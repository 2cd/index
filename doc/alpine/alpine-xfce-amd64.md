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
tag = ["xfce", "2023-09-07"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-xfce_amd64_2023-09-07_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "08b113c7b062a3a467aafc823d4a959ca79be6227e62179ee568b2d0a08868cb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.3G"
tar_bytes = 1301744128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "420M"
zstd_bytes = 439904541

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230831"
previous_tag = "2023-08-31"
previous_file = "alpine-xfce_amd64_2023-08-31_00-15-rootfs.tar.zst"
previous_sha256 = "874c8924891ff3c91395f927935d4b89b6b9b72c8cd152490f5f5d4d59eee13a"

current_version = "latest02"
current_date = "20230907"
old_file = "alpine-xfce_amd64_2023-08-24_00-16-rootfs.tar.zst"
old_sha256 = "0e25fa63b2e85876a664e6637b0c911854401ce0ca6ea107de11d875cc3ba03b"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-xfce_amd64_2023-09-07_00-16-rootfs.tar.zst
# SHA256SUM=08b113c7b062a3a467aafc823d4a959ca79be6227e62179ee568b2d0a08868cb
# BUILD_DATE=20230907
# BUILD_TAG=2023-09-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-07
begin = 2023-09-07 00:07:29.027468597+00:00
start-sync_0 = 00:09:15
start-zstd = 00:10:33
start-sync_1 = 00:15:50
end-sync_1 = 00:16:28
end = 2023-09-07 00:16:28.660468278+00:00

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
