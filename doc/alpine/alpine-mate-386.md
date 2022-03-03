# alpine-mate-386

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name alpine-mate-386 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-386 zsh
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

## alpine-mate-386.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-03-03"]
os = "alpine"
release = "edge"
arch = "i386"
platform = "linux/386"
x11_or_wayland = true

[file]
name = "alpine-mate_i386_2022-03-03_00-35.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "06738db015e2738d0616cf76ebebfd9cde716516dbc854bd13184e08f7c03a35"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "792M"
tar_bytes = 830345728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "249M"
zstd_bytes = 260442330

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220224"
previous_tag = "2022-02-24"
previous_file = "alpine-mate_i386_2022-02-24_00-33-rootfs.tar.zst"
previous_sha256 = "38ce043ec9d8a66c36bfa7eb25a68db70889b67a1930a8af46b6741cad6ae7c9"

current_version = "latest02"
current_date = "20220303"
old_file = "alpine-mate_i386_2022-02-17_00-37-rootfs.tar.zst"
old_sha256 = "b0baf582967a803387a003101d5a34d1b658c5c81af441272b2cae1713f6f142"
# edition 2021
# DISTRO_NAME=alpine-edge_i386
# ROOTFS_FILE=alpine-mate_i386_2022-03-03_00-35-rootfs.tar.zst
# SHA256SUM=06738db015e2738d0616cf76ebebfd9cde716516dbc854bd13184e08f7c03a35
# BUILD_DATE=20220303
# BUILD_TAG=2022-03-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:35

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-03
begin = 2022-03-03 00:06:33.342369762+00:00
start-sync_0 = 00:31:28
start-zstd = 00:32:14
start-sync_1 = 00:34:52
end-sync_1 = 00:35:14
end = 2022-03-03 00:35:14.102838003+00:00

[server]
repo = "cake233/alpine-mate-386"

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
ldd = 'musl libc (i386) Version 1.2.2'
zsh = 'zsh 5.8.1 (i586-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
