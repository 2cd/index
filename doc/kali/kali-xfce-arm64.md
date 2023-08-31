# kali-xfce-arm64

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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-08-31"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-08-31_13-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "78405cd1a21af3532a3be5033b7ebd9be58a2870d71e4b7d56788ef598f5187f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5302877184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1443668250

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230824"
previous_tag = "2023-08-24"
previous_file = "kali-xfce_arm64_2023-08-24_13-38-rootfs.tar.zst"
previous_sha256 = "697b372e9c03885bb62322c55e78b7cdbae1852d6c8c7b72a10cf9c3ec64bc94"

current_version = "latest01"
current_date = "20230831"
old_file = "kali-xfce_arm64_2023-08-17_13-35-rootfs.tar.zst"
old_sha256 = "dc3f80e8c69d2377c6f8e2938b59bdddf936cdda01b50fd425f2812e19abe031"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-08-31_13-45-rootfs.tar.zst
# SHA256SUM=78405cd1a21af3532a3be5033b7ebd9be58a2870d71e4b7d56788ef598f5187f
# BUILD_DATE=20230831
# BUILD_TAG=2023-08-31
# STATUS=completed
# VERSION=latest01
# END_TIME=13:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-31
begin = 2023-08-31 12:26:47.132032652+00:00
start-sync_0 = 13:15:27
start-zstd = 13:20:39
start-sync_1 = 13:42:55
end-sync_1 = 13:45:00
end = 2023-08-31 13:45:00.842026658+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
