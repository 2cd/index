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
tag = ["mate", "2023-07-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2023-07-25_01-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "90e1e3b64e131ca1ba43a8fe7ef834462b96763711ce25e152aad55fefdd1264"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4575934464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1230767198

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230718"
previous_tag = "2023-07-18"
previous_file = "ubuntu-mate_arm64_2023-07-18_00-57-rootfs.tar.zst"
previous_sha256 = "32c907d18aac2b0e84cab2a7de6cd5e3ad0bd02053cea8307a1ae0ee293e0c1e"

current_version = "latest01"
current_date = "20230725"
old_file = "ubuntu-mate_arm64_2023-07-11_00-56-rootfs.tar.zst"
old_sha256 = "d70b013d07c219cc949544d40f46800d75e2b1a60687820618752813b911930d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2023-07-25_01-04-rootfs.tar.zst
# SHA256SUM=90e1e3b64e131ca1ba43a8fe7ef834462b96763711ce25e152aad55fefdd1264
# BUILD_DATE=20230725
# BUILD_TAG=2023-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=01:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-25
begin = 2023-07-25 00:03:02.781393170+00:00
start-sync_0 = 00:41:15
start-zstd = 00:45:40
start-sync_1 = 01:03:33
end-sync_1 = 01:04:56
end = 2023-07-25 01:04:56.725331837+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
