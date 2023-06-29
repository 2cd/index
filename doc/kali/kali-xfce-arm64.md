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
tag = ["xfce", "2023-06-29"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-06-29_13-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "96dcfa24f1990e4d4782fa2d1bc76c222495fe307d14685bbaef985aa7ef6471"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5262840832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1450984015

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230622"
previous_tag = "2023-06-22"
previous_file = "kali-xfce_arm64_2023-06-22_13-29-rootfs.tar.zst"
previous_sha256 = "4b8be08af3928d70cfbf6ee29f00f8d6d3aefc21279ea6893b5ed20c86233b2c"

current_version = "latest02"
current_date = "20230629"
old_file = "kali-xfce_arm64_2023-06-15_13-30-rootfs.tar.zst"
old_sha256 = "577a449e311e608e70cb0f9d8cb186d3d15fb62b0cd981ababea95a0c5996c3c"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-06-29_13-29-rootfs.tar.zst
# SHA256SUM=96dcfa24f1990e4d4782fa2d1bc76c222495fe307d14685bbaef985aa7ef6471
# BUILD_DATE=20230629
# BUILD_TAG=2023-06-29
# STATUS=completed
# VERSION=latest02
# END_TIME=13:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-29
begin = 2023-06-29 12:25:18.707358331+00:00
start-sync_0 = 13:06:01
start-zstd = 13:10:11
start-sync_1 = 13:28:22
end-sync_1 = 13:29:49
end = 2023-06-29 13:29:49.931825017+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
