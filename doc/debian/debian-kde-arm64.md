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
tag = ["kde", "2023-06-28"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-06-28_13-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "34f7b61b51edd1ed0a6570617b21b8940b3bcfc305979599df04a7fe2b34cc0f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.1G"
tar_bytes = 6510818304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1821772104

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230621"
previous_tag = "2023-06-21"
previous_file = "debian-kde_arm64_2023-06-21_13-28-rootfs.tar.zst"
previous_sha256 = "73bdeaf7e20a4e31a1198450b75784f96a9492ea4e88d94f9f9af5337b628633"

current_version = "latest01"
current_date = "20230628"
old_file = "debian-kde_arm64_2023-06-14_13-31-rootfs.tar.zst"
old_sha256 = "9640401806ebd9fc62b61151c8ed58bc4682ae437dd3e98bcf312114e6d70794"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-06-28_13-30-rootfs.tar.zst
# SHA256SUM=34f7b61b51edd1ed0a6570617b21b8940b3bcfc305979599df04a7fe2b34cc0f
# BUILD_DATE=20230628
# BUILD_TAG=2023-06-28
# STATUS=completed
# VERSION=latest01
# END_TIME=13:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-28
begin = 2023-06-28 12:20:56.287996781+00:00
start-sync_0 = 13:00:26
start-zstd = 13:05:50
start-sync_1 = 13:28:52
end-sync_1 = 13:30:37
end = 2023-06-28 13:30:37.036867157+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
