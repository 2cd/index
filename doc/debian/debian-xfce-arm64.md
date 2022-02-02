# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-02-02"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "debian-xfce_arm64_2022-02-02_13-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "cb78c8630ec894ea34eb1bf75e57ef1761d55ebb238792f87d4aed46d5e6bcb3"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4216052224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1180736005

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220126"
previous_tag = "2022-01-26"
previous_file = "debian-xfce_arm64_2022-01-26_13-11-rootfs.tar.zst"
previous_sha256 = "bf75f783d0311dcb314a63529666f3be246bba467eac859993b5b057273213ed"

current_version = "latest01"
current_date = "20220202"
old_file = "debian-xfce_arm64_2022-01-19_13-13-rootfs.tar.zst"
old_sha256 = "50cf0461e06ccd1637c6bd6d812bcf222b043e11bd8e70062d578536831420e8"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2022-02-02_13-08-rootfs.tar.zst
# SHA256SUM=cb78c8630ec894ea34eb1bf75e57ef1761d55ebb238792f87d4aed46d5e6bcb3
# BUILD_DATE=20220202
# BUILD_TAG=2022-02-02
# STATUS=completed
# VERSION=latest01
# END_TIME=13:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-02
begin = 2022-02-02 12:21:39.013178972+00:00
start-sync_0 = 12:54:12
start-zstd = 12:57:20
start-sync_1 = 13:07:45
end-sync_1 = 13:08:58
end = 2022-02-02 13:08:58.162795987+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-5) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
