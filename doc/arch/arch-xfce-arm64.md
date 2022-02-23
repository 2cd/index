# arch-xfce-arm64

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
    --name arch-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-02-23"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "arch-xfce_arm64_2022-02-23_00-55.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2a452739765986fcab01461fa5307e86a0712a6e1a1109b7b9b7214da893d7e5"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4313104384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1362529416

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220209"
previous_tag = "2022-02-09"
previous_file = "arch-xfce_arm64_2022-02-09_01-09-rootfs.tar.zst"
previous_sha256 = "33e94332b1e5c3cbe9710b211b2d96e832e4ccefca4efbf1f93ac0a9e779b1d5"

current_version = "latest01"
current_date = "20220223"
old_file = "arch-xfce_arm64_2022-02-02_01-01-rootfs.tar.zst"
old_sha256 = "642f9a870c431707a2dc8ce920a4c46936de78630150ea753cd6c9b53b4bd1be"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2022-02-23_00-55-rootfs.tar.zst
# SHA256SUM=2a452739765986fcab01461fa5307e86a0712a6e1a1109b7b9b7214da893d7e5
# BUILD_DATE=20220223
# BUILD_TAG=2022-02-23
# STATUS=completed
# VERSION=latest01
# END_TIME=00:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-23
begin = 2022-02-23 00:28:13.258439073+00:00
start-sync_0 = 00:44:51
start-zstd = 00:48:35
start-sync_1 = 00:54:01
end-sync_1 = 00:55:26
end = 2022-02-23 00:55:26.263242725+00:00

[server]
repo = "cake233/arch-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
