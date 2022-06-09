# kali-xfce-armv7

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
    --name kali-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-armv7 zsh
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

## kali-xfce-armv7.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-06-09"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2022-06-09_13-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e00ca06c8e2d3cbee02e3c0cb67ee6c175de1f604067ab5015c0b00c4529ac7f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4903572480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1541520788

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220602"
previous_tag = "2022-06-02"
previous_file = "kali-xfce_armhf_2022-06-02_12-59-rootfs.tar.zst"
previous_sha256 = "f0c653727ec874b27c1812617d91dbd7053b0d7fe88aa101496f0f2adeb5fd55"

current_version = "latest02"
current_date = "20220609"
old_file = "kali-xfce_armhf_2022-05-26_13-25-rootfs.tar.zst"
old_sha256 = "89726897e04b38280e1bfe85c1a0f6fe2a50c5fabaff0c48d6c8849056370650"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2022-06-09_13-25-rootfs.tar.zst
# SHA256SUM=e00ca06c8e2d3cbee02e3c0cb67ee6c175de1f604067ab5015c0b00c4529ac7f
# BUILD_DATE=20220609
# BUILD_TAG=2022-06-09
# STATUS=completed
# VERSION=latest02
# END_TIME=13:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-09
begin = 2022-06-09 12:22:12.935799104+00:00
start-sync_0 = 13:06:30
start-zstd = 13:10:47
start-sync_1 = 13:24:00
end-sync_1 = 13:25:31
end = 2022-06-09 13:25:31.347257868+00:00

[server]
repo = "cake233/kali-xfce-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
