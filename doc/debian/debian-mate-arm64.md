# debian-mate-arm64

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
    --name debian-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-arm64 zsh
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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2021-12-22"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "debian-mate_arm64_2021-12-22_13-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "16d2055d1f0165e38c558744bf8c1fed9bd149255c2d41ddf6f8eb5a1312d075"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4501274112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1206650390

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211215"
previous_tag = "2021-12-15"
previous_file = "debian-mate_arm64_2021-12-15_13-19-rootfs.tar.zst"
previous_sha256 = "c68d5ab443e088d227e6dc0e93899f67bbc97e63f62c412e1ae11b3d16d92a65"

current_version = "latest02"
current_date = "20211222"
old_file = "debian-mate_arm64_2021-12-08_13-15-rootfs.tar.zst"
old_sha256 = "c41eded66ca0ca55cc0d4ff34dfbbe9e067d452dc65049692afbc9459c1ddda2"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2021-12-22_13-21-rootfs.tar.zst
# SHA256SUM=16d2055d1f0165e38c558744bf8c1fed9bd149255c2d41ddf6f8eb5a1312d075
# BUILD_DATE=20211222
# BUILD_TAG=2021-12-22
# STATUS=completed
# VERSION=latest02
# END_TIME=13:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-22
begin = 2021-12-22 12:23:09.214639263+00:00
start-sync_0 = 13:02:59
start-zstd = 13:07:23
start-sync_1 = 13:20:33
end-sync_1 = 13:21:55
end = 2021-12-22 13:21:55.687173117+00:00

[server]
repo = "cake233/debian-mate-arm64"

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
