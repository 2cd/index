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
tag = ["lxqt", "2022-12-20", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2022-12-20_00-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0b6683363044b4d2126bc841b4b6fb9af168b07445c017cc9504a8dde25206b0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4244524032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1149490052

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221213"
previous_tag = "2022-12-13"
previous_file = "ubuntu-lxqt_arm64_2022-12-13_01-03-rootfs.tar.zst"
previous_sha256 = "9743d7c8b6d5631a9682a55bc3109b2bd97333a199080d4ac488562a6f0b3b1a"

current_version = "latest01"
current_date = "20221220"
old_file = "ubuntu-lxqt_arm64_2022-12-06_01-02-rootfs.tar.zst"
old_sha256 = "8967fe5187840c3db12638d2cb84b3db121c2e41835f18c7080b07123d6d11cf"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2022-12-20_00-54-rootfs.tar.zst
# SHA256SUM=0b6683363044b4d2126bc841b4b6fb9af168b07445c017cc9504a8dde25206b0
# BUILD_DATE=20221220
# BUILD_TAG=2022-12-20
# STATUS=completed
# VERSION=latest01
# END_TIME=00:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-20
begin = 2022-12-20 00:03:20.882626226+00:00
start-sync_0 = 00:35:11
start-zstd = 00:38:24
start-sync_1 = 00:53:16
end-sync_1 = 00:54:26
end = 2022-12-20 00:54:26.433165672+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
