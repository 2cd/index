# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-12-26", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2023-12-26_02-24.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "28493bfd6af8691813be31288a8034e19c71bf0efd83fb235dc28a53fb2fb9f9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.4G"
tar_bytes = 5765890048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1559328351

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-kde_arm64_2023-11-28_01-31-rootfs.tar.zst"
previous_sha256 = "7be07739e590a892d4930d2f8cd54ae4a8b4674470a9e7ad44f2fc684a7f254d"

current_version = "latest02"
current_date = "20231226"
old_file = "ubuntu-kde_arm64_2023-11-21_01-31-rootfs.tar.zst"
old_sha256 = "6794b9c83a7e4fd1410f4af77513be4a37251da16b6b4b2630aa26b79f0e8938"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2023-12-26_02-24-rootfs.tar.zst
# SHA256SUM=28493bfd6af8691813be31288a8034e19c71bf0efd83fb235dc28a53fb2fb9f9
# BUILD_DATE=20231226
# BUILD_TAG=2023-12-26
# STATUS=completed
# VERSION=latest02
# END_TIME=02:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-26
begin = 2023-12-26 00:35:58.434538035+00:00
start-sync_0 = 02:05:38
start-zstd = 02:08:31
start-sync_1 = 02:23:34
end-sync_1 = 02:24:39
end = 2023-12-26 02:24:39.444153017+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
