# kali-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
    apt install qemu-user-static
fi

# 5903 is the host vnc port
# 5902 is the container vnc port
# 36080 is the container novnc port
docker run \
    -it \
    --shm-size 512m \
    -p 5903:5902 \
    -p 36081:36080 \
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```
    startx11vnc
```

or

```sh
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
http://localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-09-21"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-09-21_14-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e329b8db53e762005b8b4d7040b4af11c9d59abb9631ea87cdbedee56ea92786"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5331888128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1460484963

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230914"
previous_tag = "2023-09-14"
previous_file = "kali-xfce_arm64_2023-09-14_13-41-rootfs.tar.zst"
previous_sha256 = "bd6b391926497cc7a53f53ce9d34682c4d88aea244ef33eb9bde27ff6208f1c7"

current_version = "latest02"
current_date = "20230921"
old_file = "kali-xfce_arm64_2023-09-07_13-31-rootfs.tar.zst"
old_sha256 = "8992f5a2c73fb0fd756ef41b7168e870f6ff8e5b8339e35e0e39c9e6dbf174c4"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-09-21_14-01-rootfs.tar.zst
# SHA256SUM=e329b8db53e762005b8b4d7040b4af11c9d59abb9631ea87cdbedee56ea92786
# BUILD_DATE=20230921
# BUILD_TAG=2023-09-21
# STATUS=completed
# VERSION=latest02
# END_TIME=14:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-21
begin = 2023-09-21 12:25:46.864893537+00:00
start-sync_0 = 13:29:26
start-zstd = 13:35:27
start-sync_1 = 14:00:00
end-sync_1 = 14:01:50
end = 2023-09-21 14:01:50.875830799+00:00

[server]
repo = "cake233/kali-xfce-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
