# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-06-14"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2022-06-14_14-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fc74af28334ecbe8435b5a866126ffc0fdbac4a6783c4d73340f43ff370405c0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2860900864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "716M"
zstd_bytes = 749762650

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220607"
previous_tag = "2022-06-07"
previous_file = "fedora-mate_arm64_2022-06-07_14-04-rootfs.tar.zst"
previous_sha256 = "4b54e8d1b8102cdf672d021141032d5024d118515852c86613aa1331411be54b"

current_version = "latest02"
current_date = "20220614"
old_file = "fedora-mate_arm64_2022-05-31_14-10-rootfs.tar.zst"
old_sha256 = "b477d8b3ae91acba5fbbbebbb4ebd3544be2e8f3d172dc62b88f2ef51b3fd78e"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-06-14_14-14-rootfs.tar.zst
# SHA256SUM=fc74af28334ecbe8435b5a866126ffc0fdbac4a6783c4d73340f43ff370405c0
# BUILD_DATE=20220614
# BUILD_TAG=2022-06-14
# STATUS=completed
# VERSION=latest02
# END_TIME=14:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-14
begin = 2022-06-14 12:48:15.613133787+00:00
start-sync_0 = 14:00:58
start-zstd = 14:02:52
start-sync_1 = 14:13:41
end-sync_1 = 14:14:36
end = 2022-06-14 14:14:36.400400140+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
