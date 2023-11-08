# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-11-08"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-11-08_15-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7d037964a73bf4119de325585c91cd894c6628aa963ed48bfc74aeccb618a6c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.2G"
tar_bytes = 6612599296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1836990574

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231025"
previous_tag = "2023-10-25"
previous_file = "debian-kde_arm64_2023-10-25_16-12-rootfs.tar.zst"
previous_sha256 = "6a563480c96f17e50d778fd1f088630aa5e94559fb1cee18bbf49a022517856b"

current_version = "latest02"
current_date = "20231108"
old_file = "debian-kde_arm64_2023-10-04_14-53-rootfs.tar.zst"
old_sha256 = "edcb5adf9504d793842cb11cd34f38397f4309084f24760455fd7c33b8eca07a"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-11-08_15-16-rootfs.tar.zst
# SHA256SUM=a7d037964a73bf4119de325585c91cd894c6628aa963ed48bfc74aeccb618a6c
# BUILD_DATE=20231108
# BUILD_TAG=2023-11-08
# STATUS=completed
# VERSION=latest02
# END_TIME=15:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-08
begin = 2023-11-08 12:31:30.062522350+00:00
start-sync_0 = 14:38:46
start-zstd = 14:45:48
start-sync_1 = 15:14:27
end-sync_1 = 15:16:58
end = 2023-11-08 15:16:58.495065119+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
