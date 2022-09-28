# arch-mate-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name arch-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-amd64 zsh
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

## arch-mate-amd64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2022-09-28"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_amd64_2022-09-28_01-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6ebdf06b021c1dc1651c90378b1d188308eab1c8ceb01a8a6323e042ff1d2d14"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4620845568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1318080540

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220921"
previous_tag = "2022-09-21"
previous_file = "arch-mate_amd64_2022-09-21_00-54-rootfs.tar.zst"
previous_sha256 = "9e844eed2f1504c47a84ef4355dabf990ac2d6a2725d262aae3d79cc6ee7e3ae"

current_version = "latest02"
current_date = "20220928"
old_file = "arch-mate_amd64_2022-09-14_00-54-rootfs.tar.zst"
old_sha256 = "de202763f921b16db91432ce38acfbead57ce6e412b9c6769d2d652ff13a1d25"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2022-09-28_01-08-rootfs.tar.zst
# SHA256SUM=6ebdf06b021c1dc1651c90378b1d188308eab1c8ceb01a8a6323e042ff1d2d14
# BUILD_DATE=20220928
# BUILD_TAG=2022-09-28
# STATUS=completed
# VERSION=latest02
# END_TIME=01:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-28
begin = 2022-09-28 00:36:06.830927070+00:00
start-sync_0 = 00:41:37
start-zstd = 00:47:22
start-sync_1 = 01:07:20
end-sync_1 = 01:08:49
end = 2022-09-28 01:08:49.737556441+00:00

[server]
repo = "cake233/arch-mate-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
