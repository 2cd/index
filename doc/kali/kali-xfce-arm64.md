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
tag = ["xfce", "2023-10-05"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-10-05_14-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5943813fed7bf8c95fdacd26d572c6026f1010224bf51859a5c6f690ddb05053"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5321692672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1448234608

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230928"
previous_tag = "2023-09-28"
previous_file = "kali-xfce_arm64_2023-09-28_13-43-rootfs.tar.zst"
previous_sha256 = "0adf1fdecbbc9650ff2aee01c0b49b8143361a7e661205c3921c7902c606d6a8"

current_version = "latest02"
current_date = "20231005"
old_file = "kali-xfce_arm64_2023-09-21_14-01-rootfs.tar.zst"
old_sha256 = "e329b8db53e762005b8b4d7040b4af11c9d59abb9631ea87cdbedee56ea92786"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-10-05_14-26-rootfs.tar.zst
# SHA256SUM=5943813fed7bf8c95fdacd26d572c6026f1010224bf51859a5c6f690ddb05053
# BUILD_DATE=20231005
# BUILD_TAG=2023-10-05
# STATUS=completed
# VERSION=latest02
# END_TIME=14:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-05
begin = 2023-10-05 12:30:23.419614273+00:00
start-sync_0 = 14:02:00
start-zstd = 14:06:02
start-sync_1 = 14:23:54
end-sync_1 = 14:26:10
end = 2023-10-05 14:26:10.727935019+00:00

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
