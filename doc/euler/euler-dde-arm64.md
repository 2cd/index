# euler-dde-arm64

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
    --name euler-dde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/euler-dde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it euler-dde-arm64 zsh
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

## euler-dde-arm64.toml

```toml
[main]
name = "euler"
tag = ["dde", "2022-12-15"]
os = "euler"
release = "dde"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "euler-dde_arm64_2022-12-15_01-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8c0f7e8f979708d77ad0a201f0db3c1b05a0b19a9547e6835a01ec2c4426dd60"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.3G"
tar_bytes = 5598456320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1703258485

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221115"
previous_tag = "2022-11-15"
previous_file = "euler-dde_arm64_2022-11-15_01-04-rootfs.tar.zst"
previous_sha256 = "6293ac774453633b912a26f2ce4f30cb32d3462ceb6ae1832bc3d232b5d15893"

current_version = "latest01"
current_date = "20221215"
old_file = "euler-dde_arm64_2022-10-15_00-58-rootfs.tar.zst"
old_sha256 = "2a3864b1a1fde11df6a34df238564dd01f827cdef2192ddc15b12bc68c55e0cc"
# edition 2021
# DISTRO_NAME=euler_arm64
# ROOTFS_FILE=euler-dde_arm64_2022-12-15_01-05-rootfs.tar.zst
# SHA256SUM=8c0f7e8f979708d77ad0a201f0db3c1b05a0b19a9547e6835a01ec2c4426dd60
# BUILD_DATE=20221215
# BUILD_TAG=2022-12-15
# STATUS=completed
# VERSION=latest01
# END_TIME=01:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-15
begin = 2022-12-15 00:10:58.297953097+00:00
start-sync_0 = 00:44:45
start-zstd = 00:50:05
start-sync_1 = 01:03:27
end-sync_1 = 01:05:23
end = 2022-12-15 01:05:23.910098684+00:00

[server]
repo = "cake233/euler-dde-arm64"

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

[port]
tcp = [5902, 36080]
```
