# arch-mate-arm64

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
    --name arch-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-arm64 zsh
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

## arch-mate-arm64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2023-04-19"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_arm64_2023-04-19_01-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "68ddf2397382137f4f499bc0262c65cc60ba8fe1d43abbadc34658ca4a5f16d5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5395786752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1499212111

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230412"
previous_tag = "2023-04-12"
previous_file = "arch-mate_arm64_2023-04-12_01-15-rootfs.tar.zst"
previous_sha256 = "05412c4e720c9af9edea4b5edd85ae3fe45a01b89d42cf021000f900c41e8e0f"

current_version = "latest02"
current_date = "20230419"
old_file = "arch-mate_arm64_2023-04-05_01-17-rootfs.tar.zst"
old_sha256 = "316b4bb95e5a76be5d0fd32a568e07434a554d58ae28e8ad8ba58d96cdbf6e67"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2023-04-19_01-13-rootfs.tar.zst
# SHA256SUM=68ddf2397382137f4f499bc0262c65cc60ba8fe1d43abbadc34658ca4a5f16d5
# BUILD_DATE=20230419
# BUILD_TAG=2023-04-19
# STATUS=completed
# VERSION=latest02
# END_TIME=01:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-19
begin = 2023-04-19 00:30:11.457512739+00:00
start-sync_0 = 00:49:59
start-zstd = 00:54:46
start-sync_1 = 01:11:56
end-sync_1 = 01:13:24
end = 2023-04-19 01:13:24.843967568+00:00

[server]
repo = "cake233/arch-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
