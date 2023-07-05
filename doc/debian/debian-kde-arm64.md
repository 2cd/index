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
tag = ["kde", "2023-07-05"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-07-05_13-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7212175cae6a83be8b00aa062580ec44573eae656dd370e80b88bdc7d7ca1440"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2782729728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "714M"
zstd_bytes = 748555624

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230628"
previous_tag = "2023-06-28"
previous_file = "debian-kde_arm64_2023-06-28_13-30-rootfs.tar.zst"
previous_sha256 = "34f7b61b51edd1ed0a6570617b21b8940b3bcfc305979599df04a7fe2b34cc0f"

current_version = "latest02"
current_date = "20230705"
old_file = "debian-kde_arm64_2023-06-21_13-28-rootfs.tar.zst"
old_sha256 = "73bdeaf7e20a4e31a1198450b75784f96a9492ea4e88d94f9f9af5337b628633"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-07-05_13-06-rootfs.tar.zst
# SHA256SUM=7212175cae6a83be8b00aa062580ec44573eae656dd370e80b88bdc7d7ca1440
# BUILD_DATE=20230705
# BUILD_TAG=2023-07-05
# STATUS=completed
# VERSION=latest02
# END_TIME=13:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-05
begin = 2023-07-05 12:19:01.170713239+00:00
start-sync_0 = 12:54:19
start-zstd = 12:56:13
start-sync_1 = 13:05:43
end-sync_1 = 13:06:29
end = 2023-07-05 13:06:29.917517534+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-3) 2.37'
zsh = ''

[port]
tcp = [5902, 36080]
```
