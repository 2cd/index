# alpine-kde-arm64

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
    --name alpine-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/alpine-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it alpine-kde-arm64 zsh
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

## alpine-kde-arm64.toml

```toml
[main]
name = "alpine"
tag = ["kde", "2022-04-10"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "alpine-kde_arm64_2022-04-10_09-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "135353cdca42368d49215eceeef41415181c489db916e9dff53bf7bd07060a60"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1769313792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "481M"
zstd_bytes = 503354168

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220406"
previous_tag = "2022-04-06"
previous_file = "alpine-kde_arm64_2022-04-06_23-27-rootfs.tar.zst"
previous_sha256 = "99301c7b95358cb76fd7a33d89f036583c7cff537b8b70538fc1001dcfce4019"

current_version = "latest01"
current_date = "20220410"
old_file = "alpine-kde_arm64_2022-03-30_23-30-rootfs.tar.zst"
old_sha256 = "2a7fc549e7e34ca7ba6c0ada9dc9161c7cba2b900d1f369955c210c5ed86aa5a"
# edition 2021
# DISTRO_NAME=alpine-edge_arm64
# ROOTFS_FILE=alpine-kde_arm64_2022-04-10_09-21-rootfs.tar.zst
# SHA256SUM=135353cdca42368d49215eceeef41415181c489db916e9dff53bf7bd07060a60
# BUILD_DATE=20220410
# BUILD_TAG=2022-04-10
# STATUS=completed
# VERSION=latest01
# END_TIME=09:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-10
begin = 2022-04-10 08:57:15.683825136+00:00
start-sync_0 = 09:13:25
start-zstd = 09:14:58
start-sync_1 = 09:21:15
end-sync_1 = 09:21:54
end = 2022-04-10 09:21:54.519321588+00:00

[server]
repo = "cake233/alpine-kde-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
zsh = 'zsh 5.8.1 (aarch64-alpine-linux-musl)'

[port]
tcp = [5902, 36080]
```
