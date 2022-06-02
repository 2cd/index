# alpine-xfce-amd64

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
    --name alpine-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-amd64 zsh
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

## alpine-xfce-amd64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-06-02"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2022-06-02_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "11f88375d2d23a80a988adfe174c614f6ad4632e0c3778ef526be1cf4573e338"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "951M"
tar_bytes = 996899840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "323M"
zstd_bytes = 338609183

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220526"
previous_tag = "2022-05-26"
previous_file = "alpine-xfce_amd64_2022-05-26_00-12-rootfs.tar.zst"
previous_sha256 = "434afb668982f1da493cc8927fc5aae1d9d02443ab40e19c433ce0616d462893"

current_version = "latest01"
current_date = "20220602"
old_file = "alpine-xfce_amd64_2022-05-19_00-12-rootfs.tar.zst"
old_sha256 = "8bf0b5a232d2798a2f22b3e6dbdb796cccbd42bf89158502a4d6d059ba46238e"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-06-02_00-13-rootfs.tar.zst
# SHA256SUM=11f88375d2d23a80a988adfe174c614f6ad4632e0c3778ef526be1cf4573e338
# BUILD_DATE=20220602
# BUILD_TAG=2022-06-02
# STATUS=completed
# VERSION=latest01
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-02
begin = 2022-06-02 00:07:06.674488577+00:00
start-sync_0 = 00:09:14
start-zstd = 00:10:14
start-sync_1 = 00:13:13
end-sync_1 = 00:13:47
end = 2022-06-02 00:13:47.789908333+00:00

[server]
repo = "cake233/alpine-xfce-amd64"

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
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
