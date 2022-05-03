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
tag = ["xfce", "2022-05-03"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2022-05-03_14-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ae0c1654e5e6072b772ec82aca2b8065187c6d09f0a05a9befb3ea5df8bebfa2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5449479168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1564875637

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220426"
previous_tag = "2022-04-26"
previous_file = "fedora-xfce_arm64_2022-04-26_14-06-rootfs.tar.zst"
previous_sha256 = "597daf0f7babee3ed37383a2db5cd222068e753a1a9104873d85dc48a0b9feca"

current_version = "latest02"
current_date = "20220503"
old_file = "fedora-xfce_arm64_2022-04-19_14-14-rootfs.tar.zst"
old_sha256 = "d3c25faf106902bce08d3806bc97ed4813da0e9ee096bfd8717b8e4da215c946"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2022-05-03_14-05-rootfs.tar.zst
# SHA256SUM=ae0c1654e5e6072b772ec82aca2b8065187c6d09f0a05a9befb3ea5df8bebfa2
# BUILD_DATE=20220503
# BUILD_TAG=2022-05-03
# STATUS=completed
# VERSION=latest02
# END_TIME=14:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-03
begin = 2022-05-03 12:35:40.923416543+00:00
start-sync_0 = 13:40:37
start-zstd = 13:45:20
start-sync_1 = 14:04:12
end-sync_1 = 14:05:49
end = 2022-05-03 14:05:49.084872707+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
