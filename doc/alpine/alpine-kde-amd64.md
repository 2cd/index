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
tag = ["kde", "2023-05-04"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "alpine-kde_amd64_2023-05-04_00-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "43aa9a1bd7d7f92b96bac3339e42a46c6b667e1e36b95cb0e20e98a80fb1086b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1870114816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "563M"
zstd_bytes = 589398531

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230427"
previous_tag = "2023-04-27"
previous_file = "alpine-kde_amd64_2023-04-27_00-19-rootfs.tar.zst"
previous_sha256 = "3e4c15955ca71b1c3220b10382d7589f7943f2593393c88a1ca931dc6ecc9a37"

current_version = "latest02"
current_date = "20230504"
old_file = "alpine-kde_amd64_2023-04-20_00-19-rootfs.tar.zst"
old_sha256 = "5051f8367cd6b128d1185b2b329102f97d6559d0ab2035428ebc8696e4a9cb2d"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2023-05-04_00-18-rootfs.tar.zst
# SHA256SUM=43aa9a1bd7d7f92b96bac3339e42a46c6b667e1e36b95cb0e20e98a80fb1086b
# BUILD_DATE=20230504
# BUILD_TAG=2023-05-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-04
begin = 2023-05-04 00:07:07.947992226+00:00
start-sync_0 = 00:09:08
start-zstd = 00:10:47
start-sync_1 = 00:17:25
end-sync_1 = 00:18:03
end = 2023-05-04 00:18:03.430528239+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
zsh = 'zsh 5.9 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
