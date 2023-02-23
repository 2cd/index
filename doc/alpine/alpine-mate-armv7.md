# alpine-mate-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name alpine-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-armv7 zsh
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

## alpine-mate-armv7.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2023-02-23"]
os = "alpine"
release = "edge"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-mate_armhf_2023-02-23_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bc0a05afba58b8cd09c02985d1d9026838466ed8f856ba6d304aa2718f1d145a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "883M"
tar_bytes = 925434880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "314M"
zstd_bytes = 328523775

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230216"
previous_tag = "2023-02-16"
previous_file = "alpine-mate_armhf_2023-02-16_00-14-rootfs.tar.zst"
previous_sha256 = "2996db7216654792440d75631323d45bf406ca0dd85f8cf9f65ddfa0ce55db5d"

current_version = "latest01"
current_date = "20230223"
old_file = "alpine-mate_armhf_2023-02-09_00-14-rootfs.tar.zst"
old_sha256 = "45e2e47e43c2dee9ebe68a48e88ab344754199e7483bbe9a9dd4c4caa3a75d3c"
# edition 2021
# DISTRO_NAME=alpine-edge_armhf
# ROOTFS_FILE=alpine-mate_armhf_2023-02-23_00-14-rootfs.tar.zst
# SHA256SUM=bc0a05afba58b8cd09c02985d1d9026838466ed8f856ba6d304aa2718f1d145a
# BUILD_DATE=20230223
# BUILD_TAG=2023-02-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-23
begin = 2023-02-23 00:07:13.442505672+00:00
start-sync_0 = 00:09:43
start-zstd = 00:10:34
start-sync_1 = 00:13:47
end-sync_1 = 00:14:13
end = 2023-02-23 00:14:13.845858683+00:00

[server]
repo = "cake233/alpine-mate-armv7"

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
ldd = 'musl libc (armhf) Version 1.2.3'
zsh = 'zsh 5.9 (armv7-alpine-linux-musleabihf)'

[port]
tcp = [5902, 36080]
```
