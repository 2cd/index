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
tag = ["xfce", "2023-07-06"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2023-07-06_00-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4391f98f555f74a0e9ce5a87ed94b637a4e1f4a2fb86c4d2fc25c82048ca73d2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1377921536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "432M"
zstd_bytes = 452753199

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230629"
previous_tag = "2023-06-29"
previous_file = "alpine-xfce_amd64_2023-06-29_00-15-rootfs.tar.zst"
previous_sha256 = "b1e9a5b449f9dfd6f1431115757e8aed53823410f14c575dcb02f8263d06a1aa"

current_version = "latest01"
current_date = "20230706"
old_file = "alpine-xfce_amd64_2023-06-22_00-14-rootfs.tar.zst"
old_sha256 = "520c54b9b56f6f6ed52b2f4e54e4cdd47adcea1a0f2bf661a6241516256e8e10"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2023-07-06_00-15-rootfs.tar.zst
# SHA256SUM=4391f98f555f74a0e9ce5a87ed94b637a4e1f4a2fb86c4d2fc25c82048ca73d2
# BUILD_DATE=20230706
# BUILD_TAG=2023-07-06
# STATUS=completed
# VERSION=latest01
# END_TIME=00:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-06
begin = 2023-07-06 00:06:51.476151763+00:00
start-sync_0 = 00:08:26
start-zstd = 00:09:42
start-sync_1 = 00:14:39
end-sync_1 = 00:15:12
end = 2023-07-06 00:15:12.884903104+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
