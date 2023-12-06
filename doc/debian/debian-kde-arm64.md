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
tag = ["kde", "2023-12-06"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-12-06_14-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9fb7c69efba58a100c14d79c92805549b33b7d5ecb56d7283959f68d2d998460"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.3G"
tar_bytes = 6698213888

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1845435622

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-kde_arm64_2023-11-22_14-13-rootfs.tar.zst"
previous_sha256 = "c12a0b738c2e7167818ee86b292b263779bbcbb27b939b915a39af4dad55ba45"

current_version = "latest01"
current_date = "20231206"
old_file = "debian-kde_arm64_2023-11-15_15-29-rootfs.tar.zst"
old_sha256 = "3eb72845a9b5adc7f7c3018c585074fb93fea6c72ccabeb531982250d0f14d82"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-12-06_14-28-rootfs.tar.zst
# SHA256SUM=9fb7c69efba58a100c14d79c92805549b33b7d5ecb56d7283959f68d2d998460
# BUILD_DATE=20231206
# BUILD_TAG=2023-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=14:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-06
begin = 2023-12-06 12:33:15.433408438+00:00
start-sync_0 = 14:04:21
start-zstd = 14:07:48
start-sync_1 = 14:26:47
end-sync_1 = 14:28:08
end = 2023-12-06 14:28:08.053313050+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
