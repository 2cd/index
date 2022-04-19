# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2022-04-19"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "fedora-kde_arm64_2022-04-19_14-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "437ac1aff7ee911ee5832c12db270e5d6cd8b47ffec2c7d1d7ed7efe0139ac80"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.9G"
tar_bytes = 6272232960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1717717658

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220412"
previous_tag = "2022-04-12"
previous_file = "fedora-kde_arm64_2022-04-12_16-04-rootfs.tar.zst"
previous_sha256 = "55194a7f42407c4198ddfbbd66c6380c76fb13d28eaa4c8fdf540b7b6bb0637c"

current_version = "latest02"
current_date = "20220419"
old_file = "fedora-kde_arm64_2022-04-05_13-36-rootfs.tar.zst"
old_sha256 = "396ee3cf157d94c9e7516285eca4c26188a6f030fc8460b2c9640a327fe18987"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2022-04-19_14-37-rootfs.tar.zst
# SHA256SUM=437ac1aff7ee911ee5832c12db270e5d6cd8b47ffec2c7d1d7ed7efe0139ac80
# BUILD_DATE=20220419
# BUILD_TAG=2022-04-19
# STATUS=completed
# VERSION=latest02
# END_TIME=14:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-19
begin = 2022-04-19 12:47:45.213339233+00:00
start-sync_0 = 14:10:11
start-zstd = 14:16:05
start-sync_1 = 14:35:27
end-sync_1 = 14:37:20
end = 2022-04-19 14:37:20.964241236+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
