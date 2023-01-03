# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-01-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2023-01-03_01-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3a8bdd5c5a87edc0fb6236278e58a5c8cc69a62494bc19e3cfa826effad1ec28"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5052942848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1377854480

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221227"
previous_tag = "2022-12-27"
previous_file = "ubuntu-kde_arm64_2022-12-27_01-03-rootfs.tar.zst"
previous_sha256 = "95a8e24f08244a88d418e7ff45545dce7698cb73d3b41da6df00f3d062449f4d"

current_version = "latest01"
current_date = "20230103"
old_file = "ubuntu-kde_arm64_2022-12-20_03-00-rootfs.tar.zst"
old_sha256 = "c02ac4e8cab1532c538c58fd6ce259c65210263c8fa24622f459120aa78c7814"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2023-01-03_01-03-rootfs.tar.zst
# SHA256SUM=3a8bdd5c5a87edc0fb6236278e58a5c8cc69a62494bc19e3cfa826effad1ec28
# BUILD_DATE=20230103
# BUILD_TAG=2023-01-03
# STATUS=completed
# VERSION=latest01
# END_TIME=01:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-03
begin = 2023-01-03 00:03:16.635482649+00:00
start-sync_0 = 00:40:51
start-zstd = 00:45:13
start-sync_1 = 01:01:40
end-sync_1 = 01:03:00
end = 2023-01-03 01:03:00.190060469+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
