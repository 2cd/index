# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2022-12-13"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2022-12-13_14-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e1cfd25128b4333cad1c7ea69b4cbddb306cb6ea3c8583cd3126cc0f3b2943b1"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.9G"
tar_bytes = 7335450624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.9G"
zstd_bytes = 1936313400

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221206"
previous_tag = "2022-12-06"
previous_file = "fedora-kde_arm64_2022-12-06_14-41-rootfs.tar.zst"
previous_sha256 = "5aa914d8cec393cd526a0d4ad5735827fa48b1624f85962b46072e37c7c6a7a9"

current_version = "latest01"
current_date = "20221213"
old_file = "fedora-kde_arm64_2022-11-29_14-38-rootfs.tar.zst"
old_sha256 = "5067d7a8047a744235d5032d33ed7bd1ef745925f1f596893b66a01f6b34823a"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2022-12-13_14-54-rootfs.tar.zst
# SHA256SUM=e1cfd25128b4333cad1c7ea69b4cbddb306cb6ea3c8583cd3126cc0f3b2943b1
# BUILD_DATE=20221213
# BUILD_TAG=2022-12-13
# STATUS=completed
# VERSION=latest01
# END_TIME=14:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-13
begin = 2022-12-13 12:41:32.719890001+00:00
start-sync_0 = 14:21:08
start-zstd = 14:27:34
start-sync_1 = 14:52:29
end-sync_1 = 14:54:39
end = 2022-12-13 14:54:39.155697584+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
