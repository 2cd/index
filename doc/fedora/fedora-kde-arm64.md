# fedora-kde-arm64

## How to run it?

```shell
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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2021-12-14"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-kde_arm64_2021-12-14_14-51.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0324fec303c89e2da17013884538b59050944c68b883a9ae911cbcd4a69342f7"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.0G"
tar_bytes = 6394992640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1736056624

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211207"
previous_tag = "2021-12-07"
previous_file = "fedora-kde_arm64_2021-12-07_14-06-rootfs.tar.zst"
previous_sha256 = "d4a303c1bd96085c8ebfed8a2156a60776bfba01f23948955263c8a69ee6d492"

current_version = "latest02"
current_date = "20211214"
old_file = "fedora-kde_arm64_2021-11-30_17-13-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2021-12-14_14-51-rootfs.tar.zst
# SHA256SUM=0324fec303c89e2da17013884538b59050944c68b883a9ae911cbcd4a69342f7
# BUILD_DATE=20211214
# BUILD_TAG=2021-12-14
# STATUS=completed
# VERSION=latest02
# END_TIME=14:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-14
begin = 2021-12-14 13:02:35.907198661+00:00
start-sync_0 = 14:23:19
start-zstd = 14:29:32
start-sync_1 = 14:49:01
end-sync_1 = 14:51:04
end = 2021-12-14 14:51:04.969557722+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
