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
tag = ["kde", "2022-11-02"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-11-02_13-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "958aca33d96c1adee8128b4a0221b8c252ee38564300a6234b2d541fb922d784"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5860278784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1663874810

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221026"
previous_tag = "2022-10-26"
previous_file = "debian-kde_arm64_2022-10-26_13-29-rootfs.tar.zst"
previous_sha256 = "25722d06014d336e0a663e280839af5a99a52116c792ed0ab0c72610707404cd"

current_version = "latest01"
current_date = "20221102"
old_file = "debian-kde_arm64_2022-10-19_13-30-rootfs.tar.zst"
old_sha256 = "dc4a1186cf9a7225c11d6f49146e012562000c23cb5b17b736655ce6d1aac346"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-11-02_13-56-rootfs.tar.zst
# SHA256SUM=958aca33d96c1adee8128b4a0221b8c252ee38564300a6234b2d541fb922d784
# BUILD_DATE=20221102
# BUILD_TAG=2022-11-02
# STATUS=completed
# VERSION=latest01
# END_TIME=13:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-02
begin = 2022-11-02 12:22:22.007756882+00:00
start-sync_0 = 13:20:11
start-zstd = 13:27:10
start-sync_1 = 13:54:30
end-sync_1 = 13:56:30
end = 2022-11-02 13:56:30.801183071+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-3) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
