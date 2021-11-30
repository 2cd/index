# alpine-kde-amd64

## How to run it?

```shell
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

```shell
    docker exex -it alpine-kde-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## alpine-kde-amd64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2021-11-30"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "alpine-kde_amd64_2021-11-30_15-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "54b0d763a738b8fae0babdf59beab3e663375b44a4a050cc0ac951ef9577ef30"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1819695104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "549M"
zstd_bytes = 575533124

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = "2021-11-28"
last_file = "alpine-kde-amd64_2021-11-28_21-09-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211130"
old_file = "alpine-edge_amd64+kde-2021_10-28-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=alpine-edge_amd64
# ROOTFS_FILE=alpine-kde_amd64_2021-11-30_15-13-rootfs.tar.zst
# BUILD_DATE=20211130
# BUILD_TAG=2021-11-30
# STATUS=completed
# VERSION=latest01
# END_TIME=15:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-30
begin = 2021-11-30 15:00:02.400545354+00:00
start-sync_0 = 15:02:46
start-zstd = 15:04:41
start-sync_1 = 15:12:17
end-sync_1 = 15:13:00
end = 2021-11-30 15:13:00.801359773+00:00

[server]
repo = "cake233/alpine-kde-amd64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"

[version]
zsh = 'zsh 5.8 (x86_64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
