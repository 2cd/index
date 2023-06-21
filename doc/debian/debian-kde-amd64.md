# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-06-21"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2023-06-21_12-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9d63cc6418e5763f3c2aa1783b84ed8bbafcfb7f116b922c4ee93113d93baf11"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5849199104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1696426733

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230614"
previous_tag = "2023-06-14"
previous_file = "debian-kde_amd64_2023-06-14_12-56-rootfs.tar.zst"
previous_sha256 = "e6191ad776daaa02c7c6b2ea287306999454214b42188bebaa50cb9002e5bec8"

current_version = "latest02"
current_date = "20230621"
old_file = "debian-kde_amd64_2023-06-07_13-10-rootfs.tar.zst"
old_sha256 = "c557b2270682dc0311a547d94b9672a05b45ecac288962b45ded20e8a921c61c"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2023-06-21_12-53-rootfs.tar.zst
# SHA256SUM=9d63cc6418e5763f3c2aa1783b84ed8bbafcfb7f116b922c4ee93113d93baf11
# BUILD_DATE=20230621
# BUILD_TAG=2023-06-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-21
begin = 2023-06-21 12:19:02.845102178+00:00
start-sync_0 = 12:25:47
start-zstd = 12:31:18
start-sync_1 = 12:51:53
end-sync_1 = 12:53:29
end = 2023-06-21 12:53:29.926425193+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
