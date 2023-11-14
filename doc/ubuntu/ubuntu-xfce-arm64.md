# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-11-14", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2023-11-14_01-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4eac52a7d4843f1182f4eca028eea5d9e8b38159792dab7cda8e46a7c400bfe4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4844173312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1262002050

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231107"
previous_tag = "2023-11-07"
previous_file = "ubuntu-xfce_arm64_2023-11-07_01-40-rootfs.tar.zst"
previous_sha256 = "25a8034880a6c60b9fa6d10c5d5c1877b5a1f885bb151fce1de328dcd970d351"

current_version = "latest01"
current_date = "20231114"
old_file = "ubuntu-xfce_arm64_2023-10-24_01-45-rootfs.tar.zst"
old_sha256 = "058d237fe067e633e1e6f6ffcb5eafd5159be8d27ff6fcaf1eff94c641ef6a10"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2023-11-14_01-22-rootfs.tar.zst
# SHA256SUM=4eac52a7d4843f1182f4eca028eea5d9e8b38159792dab7cda8e46a7c400bfe4
# BUILD_DATE=20231114
# BUILD_TAG=2023-11-14
# STATUS=completed
# VERSION=latest01
# END_TIME=01:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-14
begin = 2023-11-14 00:23:15.804573878+00:00
start-sync_0 = 01:06:02
start-zstd = 01:08:28
start-sync_1 = 01:21:18
end-sync_1 = 01:22:21
end = 2023-11-14 01:22:21.716932223+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
