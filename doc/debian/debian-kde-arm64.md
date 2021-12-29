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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2021-12-29"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "debian-kde_arm64_2021-12-29_13-56.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "cc66fd88050e00f451f3cb531b34e45adf308934acd911177bae4a2693ec163b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5601490432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1642589291

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211222"
previous_tag = "2021-12-22"
previous_file = "debian-kde_arm64_2021-12-22_13-26-rootfs.tar.zst"
previous_sha256 = "0bc0b524572dd66318a2b345cee2763b0f3b2cd320ac329c758f1080bee5b465"

current_version = "latest01"
current_date = "20211229"
old_file = "debian-kde_arm64_2021-12-15_13-18-rootfs.tar.zst"
old_sha256 = "49cdefeab2e3ee1f9732ecc3ec4f8cbd2eb7dfaded0ba5e16eedd0b4c895d6ec"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2021-12-29_13-56-rootfs.tar.zst
# SHA256SUM=cc66fd88050e00f451f3cb531b34e45adf308934acd911177bae4a2693ec163b
# BUILD_DATE=20211229
# BUILD_TAG=2021-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=13:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-29
begin = 2021-12-29 12:23:53.432343833+00:00
start-sync_0 = 13:29:54
start-zstd = 13:36:17
start-sync_1 = 13:54:39
end-sync_1 = 13:56:30
end = 2021-12-29 13:56:30.829434981+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
