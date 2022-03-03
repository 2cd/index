# ubuntu-dde-arm64

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
    --name ubuntu-dde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-dde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-dde-arm64 zsh
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

## ubuntu-dde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["dde", "2022-03-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-dde_arm64_2022-03-03_18-52.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c177e8f23387cb84a63d0a1108c81f6ae75eb94325c0d151ea11597f5a3e5cb4"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6450073600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1845404633

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220303"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-dde_arm64_2022-03-03_18-52-rootfs.tar.zst
# SHA256SUM=c177e8f23387cb84a63d0a1108c81f6ae75eb94325c0d151ea11597f5a3e5cb4
# BUILD_DATE=20220303
# BUILD_TAG=2022-03-03
# STATUS=completed
# VERSION=latest01
# END_TIME=18:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-03
begin = 2022-03-03 16:45:41.591736364+00:00
start-sync_0 = 18:24:19
start-zstd = 18:31:33
start-sync_1 = 18:50:24
end-sync_1 = 18:52:40
end = 2022-03-03 18:52:40.210272562+00:00

[server]
repo = "cake233/ubuntu-dde-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3.2) 2.34'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
