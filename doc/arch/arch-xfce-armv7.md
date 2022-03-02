# arch-xfce-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-03-02"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "arch-xfce_armhf_2022-03-02_01-38.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "44ead37fbf1d68728167e67b2a286d2538809a32bfc1b8bbcd75c92c94ce2dc4"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3200458752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1159232985

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220223"
previous_tag = "2022-02-23"
previous_file = "arch-xfce_armhf_2022-02-23_01-36-rootfs.tar.zst"
previous_sha256 = "ec1f5a95dd2a9bdc6615cd1fffecd23accc3ff96b8f96c622d2cb3f7c893736f"

current_version = "latest02"
current_date = "20220302"
old_file = "arch-xfce_armhf_2022-02-09_01-49-rootfs.tar.zst"
old_sha256 = "c4f9ee97e6c5e096cdba133767508954dfac36859f7b9e1f1f3a2b5879c3ad73"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-03-02_01-38-rootfs.tar.zst
# SHA256SUM=44ead37fbf1d68728167e67b2a286d2538809a32bfc1b8bbcd75c92c94ce2dc4
# BUILD_DATE=20220302
# BUILD_TAG=2022-03-02
# STATUS=completed
# VERSION=latest02
# END_TIME=01:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-02
begin = 2022-03-02 00:40:00.224134952+00:00
start-sync_0 = 01:31:12
start-zstd = 01:33:46
start-sync_1 = 01:37:32
end-sync_1 = 01:38:45
end = 2022-03-02 01:38:45.561678211+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
zsh = 'zsh 5.8.1 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
