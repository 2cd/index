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

## arch-xfce-arm64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2023-08-09"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_arm64_2023-08-09_01-21.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f43dd55d416cc5454ca1af9965b039d9bee4d8cef5519b2ba2d9a6b8eb7e84de"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4504040960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1278969982

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230802"
previous_tag = "2023-08-02"
previous_file = "arch-xfce_arm64_2023-08-02_01-10-rootfs.tar.zst"
previous_sha256 = "25a5acee362c0996fc8e451533ea6a7019185a9231f1874a8e5ec1474d196119"

current_version = "latest02"
current_date = "20230809"
old_file = "arch-xfce_arm64_2023-07-26_01-11-rootfs.tar.zst"
old_sha256 = "75b65a645fda63fb868a744922a3d309672de44df485c21bbadafa236869847c"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-xfce_arm64_2023-08-09_01-21-rootfs.tar.zst
# SHA256SUM=f43dd55d416cc5454ca1af9965b039d9bee4d8cef5519b2ba2d9a6b8eb7e84de
# BUILD_DATE=20230809
# BUILD_TAG=2023-08-09
# STATUS=completed
# VERSION=latest02
# END_TIME=01:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-09
begin = 2023-08-09 00:44:13.212143891+00:00
start-sync_0 = 00:58:54
start-zstd = 01:02:43
start-sync_1 = 01:19:53
end-sync_1 = 01:21:19
end = 2023-08-09 01:21:19.342053898+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
