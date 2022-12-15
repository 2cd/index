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
tag = ["xfce", "2022-12-15"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2022-12-15_00-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a4698a907d1349b37a35e72cbfd93b87ec55af5f7a11d454e03b8345ada67692"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "989M"
tar_bytes = 1036467200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "335M"
zstd_bytes = 351229766

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221208"
previous_tag = "2022-12-08"
previous_file = "alpine-xfce_amd64_2022-12-08_00-13-rootfs.tar.zst"
previous_sha256 = "a0df605517642e60b48fc805180a2e37589747c482832712cb00d9af52bd8ca7"

current_version = "latest02"
current_date = "20221215"
old_file = "alpine-xfce_amd64_2022-12-01_00-15-rootfs.tar.zst"
old_sha256 = "bdcfc00f20d31ed8c65103c3ba0aca9ac8cfe4d22442afbf6ea211c09fafe938"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2022-12-15_00-14-rootfs.tar.zst
# SHA256SUM=a4698a907d1349b37a35e72cbfd93b87ec55af5f7a11d454e03b8345ada67692
# BUILD_DATE=20221215
# BUILD_TAG=2022-12-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-15
begin = 2022-12-15 00:07:05.049825156+00:00
start-sync_0 = 00:08:56
start-zstd = 00:09:57
start-sync_1 = 00:13:43
end-sync_1 = 00:14:11
end = 2022-12-15 00:14:11.825439585+00:00

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
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
