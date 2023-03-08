# arch-kde-arm64

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
    --name arch-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-arm64 zsh
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

## arch-kde-arm64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2023-03-08"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2023-03-08_01-26.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "684a0f85914104d89d09e394aa6325c650945b03959d6a779dda6ebb6f91f337"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5338713600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1561571532

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230301"
previous_tag = "2023-03-01"
previous_file = "arch-kde_arm64_2023-03-01_01-27-rootfs.tar.zst"
previous_sha256 = "394cffde7e8138d891405128f72a65a1b9b6c676b4d768962396c2444584e4a0"

current_version = "latest01"
current_date = "20230308"
old_file = "arch-kde_arm64_2023-02-22_01-29-rootfs.tar.zst"
old_sha256 = "6207a25a8d1571c0fff5b88ed5b1b53e05e53cf1ff166ea1a05929e5c41db057"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2023-03-08_01-26-rootfs.tar.zst
# SHA256SUM=684a0f85914104d89d09e394aa6325c650945b03959d6a779dda6ebb6f91f337
# BUILD_DATE=20230308
# BUILD_TAG=2023-03-08
# STATUS=completed
# VERSION=latest01
# END_TIME=01:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-08
begin = 2023-03-08 00:30:37.277352673+00:00
start-sync_0 = 00:55:17
start-zstd = 01:01:34
start-sync_1 = 01:24:34
end-sync_1 = 01:26:19
end = 2023-03-08 01:26:19.369779350+00:00

[server]
repo = "cake233/arch-kde-arm64"

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
