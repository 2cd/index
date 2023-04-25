# arch-xfce-arm64

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
    --name arch-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-arm64 zsh
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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2023-04-25"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_arm64_2023-04-25_23-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "35fd6c5d1fda7ad80a1566b454855b33f73a5aee72ee23fe18684b686d45081c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4513337344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1289188333

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230419"
previous_tag = "2023-04-19"
previous_file = "arch-xfce_arm64_2023-04-19_01-19-rootfs.tar.zst"
previous_sha256 = "3517c2b52810c7122d4740f2337c840c863c0557f0db09fe365a5d2c6c57b592"

current_version = "latest01"
current_date = "20230425"
old_file = "arch-xfce_arm64_2023-04-12_01-07-rootfs.tar.zst"
old_sha256 = "e9e715a42aa80259846eb8c636f308042c218ecc52ebd12c9834b70cc0c35e09"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2023-04-25_23-26-rootfs.tar.zst
# SHA256SUM=35fd6c5d1fda7ad80a1566b454855b33f73a5aee72ee23fe18684b686d45081c
# BUILD_DATE=20230425
# BUILD_TAG=2023-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=23:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-25
begin = 2023-04-25 22:38:13.344177314+00:00
start-sync_0 = 23:00:27
start-zstd = 23:05:09
start-sync_1 = 23:25:20
end-sync_1 = 23:26:46
end = 2023-04-25 23:26:46.493781994+00:00

[server]
repo = "cake233/arch-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
