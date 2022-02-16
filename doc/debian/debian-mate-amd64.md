# debian-mate-amd64

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
    --name debian-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-amd64 zsh
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

## debian-mate-amd64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2022-02-16"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-mate_amd64_2022-02-16_12-43.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "932fc0cc88389e9f8cda2aa79035c63159a0b9db10dd7e1a9ae40d58a9512331"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3952374272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1083680333

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220209"
previous_tag = "2022-02-09"
previous_file = "debian-mate_amd64_2022-02-09_12-44-rootfs.tar.zst"
previous_sha256 = "6da4c516bab1043b6c05a5287b941dd0a67817212c5264b08ec756230626ae9c"

current_version = "latest01"
current_date = "20220216"
old_file = "debian-mate_amd64_2022-02-02_12-46-rootfs.tar.zst"
old_sha256 = "92399c896f7f7a5c6d447f9341f8d126c10467545d9eadbfd600741e0c5d99c0"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2022-02-16_12-43-rootfs.tar.zst
# SHA256SUM=932fc0cc88389e9f8cda2aa79035c63159a0b9db10dd7e1a9ae40d58a9512331
# BUILD_DATE=20220216
# BUILD_TAG=2022-02-16
# STATUS=completed
# VERSION=latest01
# END_TIME=12:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-16
begin = 2022-02-16 12:23:39.594758058+00:00
start-sync_0 = 12:29:11
start-zstd = 12:32:39
start-sync_1 = 12:41:55
end-sync_1 = 12:43:04
end = 2022-02-16 12:43:04.159995880+00:00

[server]
repo = "cake233/debian-mate-amd64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
