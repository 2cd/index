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
tag = ["kde", "2022-05-25"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2022-05-25_01-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "105237ce57f2c5ab141097cc18b03b81a883daaf8ebf2ad9c14fcc5c7bd56dc8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5263001088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1481270458

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220518"
previous_tag = "2022-05-18"
previous_file = "arch-kde_arm64_2022-05-18_01-10-rootfs.tar.zst"
previous_sha256 = "5f9accaf5b66eda5c6f2514f9a7837f7d3d5cf01404a3f668baee4e5bb5dcfd3"

current_version = "latest01"
current_date = "20220525"
old_file = "arch-kde_arm64_2022-05-11_01-24-rootfs.tar.zst"
old_sha256 = "8ca6b3ceda62878827f1717c43c769dcf5f608e088bd9afc5d3f71a90060b9ea"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2022-05-25_01-11-rootfs.tar.zst
# SHA256SUM=105237ce57f2c5ab141097cc18b03b81a883daaf8ebf2ad9c14fcc5c7bd56dc8
# BUILD_DATE=20220525
# BUILD_TAG=2022-05-25
# STATUS=completed
# VERSION=latest01
# END_TIME=01:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-25
begin = 2022-05-25 00:29:50.793690464+00:00
start-sync_0 = 00:48:24
start-zstd = 00:53:20
start-sync_1 = 01:10:30
end-sync_1 = 01:11:58
end = 2022-05-25 01:11:58.671044450+00:00

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
