# alpine-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name alpine-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-xfce-arm64 zsh
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

## alpine-xfce-arm64.toml

```toml
[main]
name = "alpine"
tag = ["xfce", "2022-03-30"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-xfce_arm64_2022-03-30_23-31.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3438b6b980a58363fb79d4149af2799a312a371a84507f91037904ffb59c62d8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "871M"
tar_bytes = 913274368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "309M"
zstd_bytes = 323157888

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220324"
previous_tag = "2022-03-24"
previous_file = "alpine-xfce_arm64_2022-03-24_00-35-rootfs.tar.zst"
previous_sha256 = "4bbbf15bb51fcbb97d072cd9254cb19875a9a5e87ffe5a8eeb062497cc11bb07"

current_version = "latest01"
current_date = "20220330"
old_file = "alpine-xfce_arm64_2022-03-17_00-30-rootfs.tar.zst"
old_sha256 = "6f8e72c7912a63958b9fe05ef99e9fcce6c377355fa4b5f28479ff8de3a14468"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-xfce_arm64_2022-03-30_23-31-rootfs.tar.zst
# SHA256SUM=3438b6b980a58363fb79d4149af2799a312a371a84507f91037904ffb59c62d8
# BUILD_DATE=20220330
# BUILD_TAG=2022-03-30
# STATUS=completed
# VERSION=latest01
# END_TIME=23:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-30
begin = 2022-03-30 23:06:35.735228987+00:00
start-sync_0 = 23:26:52
start-zstd = 23:27:50
start-sync_1 = 23:30:51
end-sync_1 = 23:31:15
end = 2022-03-30 23:31:15.985387966+00:00

[server]
repo = "cake233/alpine-xfce-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.2'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
