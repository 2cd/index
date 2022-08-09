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
tag = ["lxqt", "2022-08-09", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2022-08-09_01-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "52dd190ab5b2eb38868e3ff02b8dbba8603ebe7212b62e7643cc0de673453d3b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4189772288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1147155705

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-lxqt_arm64_2022-07-12_01-20-rootfs.tar.zst"
previous_sha256 = "2a2e6261ddd809d7b2d90c2cf9456f8e589cd219d0c005875b932e9829210827"

current_version = "latest02"
current_date = "20220809"
old_file = "ubuntu-lxqt_arm64_2022-07-05_01-08-rootfs.tar.zst"
old_sha256 = "86494d27076680491b95d1cffc286b61243218fc3043f8d6eda0ad48a2dad656"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2022-08-09_01-30-rootfs.tar.zst
# SHA256SUM=52dd190ab5b2eb38868e3ff02b8dbba8603ebe7212b62e7643cc0de673453d3b
# BUILD_DATE=20220809
# BUILD_TAG=2022-08-09
# STATUS=completed
# VERSION=latest02
# END_TIME=01:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-09
begin = 2022-08-09 00:23:50.553179029+00:00
start-sync_0 = 01:06:58
start-zstd = 01:11:01
start-sync_1 = 01:29:38
end-sync_1 = 01:30:56
end = 2022-08-09 01:30:56.232341898+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
