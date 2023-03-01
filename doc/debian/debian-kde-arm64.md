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
tag = ["kde", "2023-03-01"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-03-01_13-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b4a61a709992a93fd681ac8aba594019aab7a035a24ce6fce9c8ced671e8300b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6472403456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1811277246

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230222"
previous_tag = "2023-02-22"
previous_file = "debian-kde_arm64_2023-02-22_13-30-rootfs.tar.zst"
previous_sha256 = "4f0a022fc9e08c7f763783291cec4cda7bc2edccf013e9c3dc3a77caf795b5d7"

current_version = "latest02"
current_date = "20230301"
old_file = "debian-kde_arm64_2023-02-15_13-33-rootfs.tar.zst"
old_sha256 = "b9a088efd0face8d550212359ea385f67332a9a1085a0f51bbd866441d3666b1"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-03-01_13-30-rootfs.tar.zst
# SHA256SUM=b4a61a709992a93fd681ac8aba594019aab7a035a24ce6fce9c8ced671e8300b
# BUILD_DATE=20230301
# BUILD_TAG=2023-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=13:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-01
begin = 2023-03-01 12:21:54.927511682+00:00
start-sync_0 = 13:01:28
start-zstd = 13:06:57
start-sync_1 = 13:28:26
end-sync_1 = 13:30:13
end = 2023-03-01 13:30:13.539834268+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
