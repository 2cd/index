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
tag = ["xfce", "2023-08-24"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2023-08-24_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0e25fa63b2e85876a664e6637b0c911854401ce0ca6ea107de11d875cc3ba03b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1300285952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "420M"
zstd_bytes = 439370614

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230817"
previous_tag = "2023-08-17"
previous_file = "alpine-xfce_amd64_2023-08-17_00-16-rootfs.tar.zst"
previous_sha256 = "69aef9b6bd7c13eb8cf8636cd65ff1e2579d1cf3728dae757de82d24eec59961"

current_version = "latest02"
current_date = "20230824"
old_file = "alpine-xfce_amd64_2023-08-10_00-16-rootfs.tar.zst"
old_sha256 = "6035c195ade54abcb8c79167ccef4360966a3b8fdeeda667596521163060cb7d"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2023-08-24_00-16-rootfs.tar.zst
# SHA256SUM=0e25fa63b2e85876a664e6637b0c911854401ce0ca6ea107de11d875cc3ba03b
# BUILD_DATE=20230824
# BUILD_TAG=2023-08-24
# STATUS=completed
# VERSION=latest02
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-24
begin = 2023-08-24 00:07:32.217092537+00:00
start-sync_0 = 00:09:01
start-zstd = 00:10:18
start-sync_1 = 00:15:29
end-sync_1 = 00:16:06
end = 2023-08-24 00:16:06.283233186+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
