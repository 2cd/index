# alpine-mate-amd64

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
    --name alpine-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-mate-amd64 zsh
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

## alpine-mate-amd64.toml

```toml
[main]
name = "alpine"
tag = ["mate", "2022-04-14"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "alpine-mate_amd64_2022-04-14_00-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ef7c3d9a02190daddcf62b83ff1acbd2155cb16e8f141d631a021f86aedf5df6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.1G"
tar_bytes = 1084889088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "327M"
zstd_bytes = 342877033

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220410"
previous_tag = "2022-04-10"
previous_file = "alpine-mate_amd64_2022-04-10_09-03-rootfs.tar.zst"
previous_sha256 = "0f0960091eef9461887268d758efdcdfce4d5396bc2f0a4d35ead39da2abb15f"

current_version = "latest02"
current_date = "20220414"
old_file = "alpine-mate_amd64_2022-04-06_23-12-rootfs.tar.zst"
old_sha256 = "5d8eb519fbd74a79a52877151f3fdea98b3a327a705516be031ca3820d8790a7"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-mate_amd64_2022-04-14_00-13-rootfs.tar.zst
# SHA256SUM=ef7c3d9a02190daddcf62b83ff1acbd2155cb16e8f141d631a021f86aedf5df6
# BUILD_DATE=20220414
# BUILD_TAG=2022-04-14
# STATUS=completed
# VERSION=latest02
# END_TIME=00:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-14
begin = 2022-04-14 00:06:31.387644951+00:00
start-sync_0 = 00:08:30
start-zstd = 00:09:29
start-sync_1 = 00:12:33
end-sync_1 = 00:13:02
end = 2022-04-14 00:13:03.008595430+00:00

[server]
repo = "cake233/alpine-mate-amd64"

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
