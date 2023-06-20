# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-06-20"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2023-06-20_14-39.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "01ba92a70690e8cb183c4d058030385d2f9879dff4141525b837fa802c96d3e0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.8G"
tar_bytes = 6176043520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1576386258

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230613"
previous_tag = "2023-06-13"
previous_file = "fedora-xfce_arm64_2023-06-13_14-52-rootfs.tar.zst"
previous_sha256 = "61e33b8233c2991ff0ba3b330ee1d0795719d07914ae56d09f3d87ada6fa0b05"

current_version = "latest01"
current_date = "20230620"
old_file = "fedora-xfce_arm64_2023-06-06_13-51-rootfs.tar.zst"
old_sha256 = "623fd7175020438f5466c22e22539cca69fdce8ce00ca4280e8aacdd46137d26"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2023-06-20_14-39-rootfs.tar.zst
# SHA256SUM=01ba92a70690e8cb183c4d058030385d2f9879dff4141525b837fa802c96d3e0
# BUILD_DATE=20230620
# BUILD_TAG=2023-06-20
# STATUS=completed
# VERSION=latest01
# END_TIME=14:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-20
begin = 2023-06-20 12:51:51.560666737+00:00
start-sync_0 = 14:15:36
start-zstd = 14:20:32
start-sync_1 = 14:38:23
end-sync_1 = 14:39:59
end = 2023-06-20 14:39:59.862519989+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
