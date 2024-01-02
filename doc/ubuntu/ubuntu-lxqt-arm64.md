# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2024-01-02", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2024-01-02_02-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "779574904930754beaaac67c480d18629396a8d5ec6db6fdbb8c4460c4ccea61"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4964617216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1299625721

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-lxqt_arm64_2023-11-28_01-21-rootfs.tar.zst"
previous_sha256 = "77762ee6b323144a2b718afe124cb5abb79d74638837a6dee9d0bda7319eae3f"

current_version = "latest02"
current_date = "20240102"
old_file = "ubuntu-lxqt_arm64_2023-11-21_01-23-rootfs.tar.zst"
old_sha256 = "c83716271055d9762f996e86ec735de89c9cb1f91ffcc7e2705631fbbb5e478d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2024-01-02_02-14-rootfs.tar.zst
# SHA256SUM=779574904930754beaaac67c480d18629396a8d5ec6db6fdbb8c4460c4ccea61
# BUILD_DATE=20240102
# BUILD_TAG=2024-01-02
# STATUS=completed
# VERSION=latest02
# END_TIME=02:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-02
begin = 2024-01-02 00:36:12.950312054+00:00
start-sync_0 = 01:58:14
start-zstd = 02:00:47
start-sync_1 = 02:13:20
end-sync_1 = 02:14:14
end = 2024-01-02 02:14:14.333783872+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
