# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2022-05-24", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2022-05-24_01-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3c43bbc574a0daaa6b5c1d6a3e74a795472e338f490070ad1bcd7ed8504b621f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4069655040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1119872212

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220517"
previous_tag = "2022-05-17"
previous_file = "ubuntu-mate_arm64_2022-05-17_01-26-rootfs.tar.zst"
previous_sha256 = "5f0f26d19bd60f29ae59d2ab393f6019da61bf8c244ad4be931f8c57ab2543a3"

current_version = "latest02"
current_date = "20220524"
old_file = "ubuntu-mate_arm64_2022-05-10_01-13-rootfs.tar.zst"
old_sha256 = "0097beb650df6d77c7971027e47efac576fd104cb95b2356fa9a909f9da1f2a9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2022-05-24_01-05-rootfs.tar.zst
# SHA256SUM=3c43bbc574a0daaa6b5c1d6a3e74a795472e338f490070ad1bcd7ed8504b621f
# BUILD_DATE=20220524
# BUILD_TAG=2022-05-24
# STATUS=completed
# VERSION=latest02
# END_TIME=01:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-24
begin = 2022-05-24 00:18:57.886448548+00:00
start-sync_0 = 00:47:40
start-zstd = 00:51:11
start-sync_1 = 01:04:35
end-sync_1 = 01:05:46
end = 2022-05-24 01:05:46.716491959+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
