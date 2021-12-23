# alpine-kde-amd64

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
    --name alpine-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2021-12-23"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-kde_amd64_2021-12-23_00-19.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1f6ca87f907acf6a6d05954f143bebdea221b5d0e525c478ad3c903ff7b4efe2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1800721920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "545M"
zstd_bytes = 571362365

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211216"
previous_tag = "2021-12-16"
previous_file = "alpine-kde_amd64_2021-12-16_00-17-rootfs.tar.zst"
previous_sha256 = "950938d975394ac8cc70177423b481655a7797b6dddcb74605d45cee481f7951"

current_version = "latest01"
current_date = "20211223"
old_file = "alpine-kde_amd64_2021-12-09_00-17-rootfs.tar.zst"
old_sha256 = "c6c5d8c9f16d6359bfdbb1ee816db21b521d8396d1b0edc0526351d03d8edf34"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2021-12-23_00-19-rootfs.tar.zst
# SHA256SUM=1f6ca87f907acf6a6d05954f143bebdea221b5d0e525c478ad3c903ff7b4efe2
# BUILD_DATE=20211223
# BUILD_TAG=2021-12-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:19

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-23
begin = 2021-12-23 00:06:31.166254602+00:00
start-sync_0 = 00:09:11
start-zstd = 00:11:09
start-sync_1 = 00:18:54
end-sync_1 = 00:19:38
end = 2021-12-23 00:19:38.037066926+00:00

[server]
repo = "cake233/alpine-kde-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (x86_64) Version 1.2.2'
zsh = 'zsh 5.8 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
