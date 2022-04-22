# manjaro-xfce-arm64

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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-04-22"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "manjaro-xfce_arm64_2022-04-22_12-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1baf9debf405d901bda820ba805b5bb9aefc4a9248df25253cd92c55d5310221"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4456185344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1294196518

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220415"
previous_tag = "2022-04-15"
previous_file = "manjaro-xfce_arm64_2022-04-15_12-53-rootfs.tar.zst"
previous_sha256 = "776e25569fb450d3d5325f5fff10ac5069b6e450ccc15ef138d461385e7a2d9c"

current_version = "latest01"
current_date = "20220422"
old_file = "manjaro-xfce_arm64_2022-04-08_11-56-rootfs.tar.zst"
old_sha256 = "8ed69c078ec95e5287dd01fcbc5dfd0d10c5dce048f4e5b6eab5e6d0c9e515c4"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2022-04-22_12-56-rootfs.tar.zst
# SHA256SUM=1baf9debf405d901bda820ba805b5bb9aefc4a9248df25253cd92c55d5310221
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 12:17:38.951687108+00:00
start-sync_0 = 12:32:08
start-zstd = 12:36:48
start-sync_1 = 12:54:50
end-sync_1 = 12:56:15
end = 2022-04-22 12:56:15.618500314+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
