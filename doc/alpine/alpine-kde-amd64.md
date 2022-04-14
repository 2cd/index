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

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-04-14"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "alpine-kde_amd64_2022-04-14_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a152922a53389d2505b2086283df0a2c7c371a45b0344826643a0f5c54c66a3a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1823610880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "493M"
zstd_bytes = 516043046

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220410"
previous_tag = "2022-04-10"
previous_file = "alpine-kde_amd64_2022-04-10_09-10-rootfs.tar.zst"
previous_sha256 = "6ef80e2e0214fd1d78cc4935df66ce0d4712523e7d11b1a2ec0fbe41ea362a55"

current_version = "latest02"
current_date = "20220414"
old_file = "alpine-kde_amd64_2022-04-06_23-18-rootfs.tar.zst"
old_sha256 = "3aea2b9ad91ffa5fa398759a6d5084f80212a27c0c078fc07613832f919db580"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2022-04-14_00-16-rootfs.tar.zst
# SHA256SUM=a152922a53389d2505b2086283df0a2c7c371a45b0344826643a0f5c54c66a3a
# BUILD_DATE=20220414
# BUILD_TAG=2022-04-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-14
begin = 2022-04-14 00:06:33.242565769+00:00
start-sync_0 = 00:08:40
start-zstd = 00:10:19
start-sync_1 = 00:16:20
end-sync_1 = 00:16:57
end = 2022-04-14 00:16:57.422848881+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
zsh = 'zsh 5.8.1 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
