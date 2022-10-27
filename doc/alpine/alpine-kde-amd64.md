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
tag = ["kde", "2022-10-27"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_amd64_2022-10-27_00-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ea6301f81649b3c6101c6078b45599fb5f313ff5e25d93c30104527793b87261"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1891492352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "531M"
zstd_bytes = 556410801

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221020"
previous_tag = "2022-10-20"
previous_file = "alpine-kde_amd64_2022-10-20_00-18-rootfs.tar.zst"
previous_sha256 = "8538b74a8cc22477a7c58a485c22a30c6e156767bcde27e32398e444f69b2316"

current_version = "latest02"
current_date = "20221027"
old_file = "alpine-kde_amd64_2022-10-13_00-20-rootfs.tar.zst"
old_sha256 = "63ac871d82c0dfc7e6e39df7d880a2358d1d6e23a8d65387b760b0ebd411558d"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2022-10-27_00-18-rootfs.tar.zst
# SHA256SUM=ea6301f81649b3c6101c6078b45599fb5f313ff5e25d93c30104527793b87261
# BUILD_DATE=20221027
# BUILD_TAG=2022-10-27
# STATUS=completed
# VERSION=latest02
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-27
begin = 2022-10-27 00:07:08.886550392+00:00
start-sync_0 = 00:09:21
start-zstd = 00:11:14
start-sync_1 = 00:18:19
end-sync_1 = 00:18:55
end = 2022-10-27 00:18:55.859214203+00:00

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
