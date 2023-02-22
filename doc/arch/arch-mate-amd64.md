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
tag = ["mate", "2023-02-22"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_amd64_2023-02-22_01-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "08b33ab65d1c93b2fb513652606240bc4266a3a068d01c6fc18d1b5cec34d61e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4747995648

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1357662914

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230215"
previous_tag = "2023-02-15"
previous_file = "arch-mate_amd64_2023-02-15_01-06-rootfs.tar.zst"
previous_sha256 = "72fa1f53f4b2307db7370b6e427a7e759f19811d493baac938229069060c7668"

current_version = "latest01"
current_date = "20230222"
old_file = "arch-mate_amd64_2023-02-08_01-12-rootfs.tar.zst"
old_sha256 = "21d623765b50c94eac97933b24a68d0b6a05d8d1d1fb2ce46a726744223e9f8a"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2023-02-22_01-04-rootfs.tar.zst
# SHA256SUM=08b33ab65d1c93b2fb513652606240bc4266a3a068d01c6fc18d1b5cec34d61e
# BUILD_DATE=20230222
# BUILD_TAG=2023-02-22
# STATUS=completed
# VERSION=latest01
# END_TIME=01:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-22
begin = 2023-02-22 00:38:58.969815278+00:00
start-sync_0 = 00:43:06
start-zstd = 00:47:39
start-sync_1 = 01:03:30
end-sync_1 = 01:04:44
end = 2023-02-22 01:04:44.370162025+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
