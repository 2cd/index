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
tag = ["xfce", "2023-12-21"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-12-21_14-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b1f744648831ee07c6407ef37a4e8e426ea6378d832d9d29a287f0de0e30efa5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5345662464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1459494976

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231123"
previous_tag = "2023-11-23"
previous_file = "kali-xfce_arm64_2023-11-23_14-14-rootfs.tar.zst"
previous_sha256 = "a30b80d59b73f8a22bd31c413a52f533c48a37b6e4c151e754e157677731403e"

current_version = "latest01"
current_date = "20231221"
old_file = "kali-xfce_arm64_2023-11-16_14-11-rootfs.tar.zst"
old_sha256 = "737a22bc1354df9978f81fc124bf917bde85caa25346714c9ae7558ebf3f4dde"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-12-21_14-11-rootfs.tar.zst
# SHA256SUM=b1f744648831ee07c6407ef37a4e8e426ea6378d832d9d29a287f0de0e30efa5
# BUILD_DATE=20231221
# BUILD_TAG=2023-12-21
# STATUS=completed
# VERSION=latest01
# END_TIME=14:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-21
begin = 2023-12-21 12:31:49.630185401+00:00
start-sync_0 = 13:53:27
start-zstd = 13:56:12
start-sync_1 = 14:09:59
end-sync_1 = 14:11:05
end = 2023-12-21 14:11:05.251922772+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
