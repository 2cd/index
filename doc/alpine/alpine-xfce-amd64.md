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
tag = ["xfce", "2022-04-21"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "alpine-xfce_amd64_2022-04-21_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "be53d04f1b6e9655d0ffbb931e9052215b1b372d277686263e2895f7dd42cc31"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "972M"
tar_bytes = 1018927104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "329M"
zstd_bytes = 344508889

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220414"
previous_tag = "2022-04-14"
previous_file = "alpine-xfce_amd64_2022-04-14_00-12-rootfs.tar.zst"
previous_sha256 = "82d2d206a22b50b77453b5c269d745dda4e4bee5e43823f7e8b1614ef4e4492a"

current_version = "latest01"
current_date = "20220421"
old_file = "alpine-xfce_amd64_2022-04-10_09-04-rootfs.tar.zst"
old_sha256 = "c8944e128a5aa57ee622eaf2cbec7fae9a57d83927134ec9da37a0189eb8d953"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-04-21_00-14-rootfs.tar.zst
# SHA256SUM=be53d04f1b6e9655d0ffbb931e9052215b1b372d277686263e2895f7dd42cc31
# BUILD_DATE=20220421
# BUILD_TAG=2022-04-21
# STATUS=completed
# VERSION=latest01
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-21
begin = 2022-04-21 00:06:10.086766023+00:00
start-sync_0 = 00:09:11
start-zstd = 00:10:22
start-sync_1 = 00:14:14
end-sync_1 = 00:14:47
end = 2022-04-21 00:14:47.193410401+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
