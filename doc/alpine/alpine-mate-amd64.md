# alpine-mate-amd64

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
    --name alpine-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-amd64 zsh
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

## alpine-mate-amd64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-09-29"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_amd64_2022-09-29_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a62a63103883fdcf7a411fab04b751b380bf1dcca30f8fe1c2c2009203bc736e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1106503680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "330M"
zstd_bytes = 345189125

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220922"
previous_tag = "2022-09-22"
previous_file = "alpine-mate_amd64_2022-09-22_00-14-rootfs.tar.zst"
previous_sha256 = "db3006a3b658f3447e9d36e79ebc69b1f061d037cd4086e0e8eb9325cb2fb3b1"

current_version = "latest02"
current_date = "20220929"
old_file = "alpine-mate_amd64_2022-09-15_00-13-rootfs.tar.zst"
old_sha256 = "368815603be9bcd67d5a52cdf4ab9e19dbe8f80fae0b66e7ee55cb325c081d2b"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2022-09-29_00-15-rootfs.tar.zst
# SHA256SUM=a62a63103883fdcf7a411fab04b751b380bf1dcca30f8fe1c2c2009203bc736e
# BUILD_DATE=20220929
# BUILD_TAG=2022-09-29
# STATUS=completed
# VERSION=latest02
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-29
begin = 2022-09-29 00:07:30.667554314+00:00
start-sync_0 = 00:09:38
start-zstd = 00:10:45
start-sync_1 = 00:15:01
end-sync_1 = 00:15:35
end = 2022-09-29 00:15:35.115631979+00:00

[server]
repo = "cake233/alpine-mate-amd64"

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
LANG = "C.UTF-8"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
