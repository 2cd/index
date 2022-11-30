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

## debian-mate-arm64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2022-11-30"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_arm64_2022-11-30_13-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0ac932656944acbd3f800025867d9b0c5b389ff9895854072c89f04350091df0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4443893760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1190082342

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221123"
previous_tag = "2022-11-23"
previous_file = "debian-mate_arm64_2022-11-23_13-11-rootfs.tar.zst"
previous_sha256 = "04f4f42343241e74964c5366243ffdc0a6800e94c9886e79df4959d474fabb67"

current_version = "latest01"
current_date = "20221130"
old_file = "debian-mate_arm64_2022-11-16_13-11-rootfs.tar.zst"
old_sha256 = "5151237708b44e54b93905c7296ffa9afa72dbad06b7f59dfb30b633ed5b93fe"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-mate_arm64_2022-11-30_13-12-rootfs.tar.zst
# SHA256SUM=0ac932656944acbd3f800025867d9b0c5b389ff9895854072c89f04350091df0
# BUILD_DATE=20221130
# BUILD_TAG=2022-11-30
# STATUS=completed
# VERSION=latest01
# END_TIME=13:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-30
begin = 2022-11-30 12:20:47.747123938+00:00
start-sync_0 = 12:53:27
start-zstd = 12:56:53
start-sync_1 = 13:11:36
end-sync_1 = 13:12:48
end = 2022-11-30 13:12:48.133822889+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
