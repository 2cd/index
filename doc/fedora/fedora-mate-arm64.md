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
tag = ["mate", "2022-05-17"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2022-05-17_13-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ffd6873e13b1bfe96204f8bd3cb17fa6bca8c98df06bafde7df4885e16bfee1d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2842206208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "710M"
zstd_bytes = 743804509

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220510"
previous_tag = "2022-05-10"
previous_file = "fedora-mate_arm64_2022-05-10_14-13-rootfs.tar.zst"
previous_sha256 = "98b0c4626c876b736146d68c5f87087b86c35b16720e78289375ee34bbe51e0d"

current_version = "latest02"
current_date = "20220517"
old_file = "fedora-mate_arm64_2022-05-03_16-18-rootfs.tar.zst"
old_sha256 = "2bf0066269c0669c4760496d12718479e951f7797446341782af1ab909c42e44"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-05-17_13-56-rootfs.tar.zst
# SHA256SUM=ffd6873e13b1bfe96204f8bd3cb17fa6bca8c98df06bafde7df4885e16bfee1d
# BUILD_DATE=20220517
# BUILD_TAG=2022-05-17
# STATUS=completed
# VERSION=latest02
# END_TIME=13:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-17
begin = 2022-05-17 12:43:27.007123604+00:00
start-sync_0 = 13:45:12
start-zstd = 13:46:53
start-sync_1 = 13:55:44
end-sync_1 = 13:56:33
end = 2022-05-17 13:56:33.223337716+00:00

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
