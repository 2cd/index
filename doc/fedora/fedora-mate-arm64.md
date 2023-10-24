# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2023-10-24"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2023-10-24_15-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "046c238e536231d90740325a32333cf9f24122f3b980a2adfd6ea1a0b2bae998"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.9G"
tar_bytes = 7309036032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1775024695

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230919"
previous_tag = "2023-09-19"
previous_file = "fedora-mate_arm64_2023-09-19_15-43-rootfs.tar.zst"
previous_sha256 = "d4ea85daf52dd1304dd3f2a1eb62511d1ed7789b17bbf3cefc751ffd934467b8"

current_version = "latest02"
current_date = "20231024"
old_file = "fedora-mate_arm64_2023-09-12_14-35-rootfs.tar.zst"
old_sha256 = "8e8b8bee8f447ff199d1fe01a267fd76f2e3cf88e1893c37869f7d9e272a0fb6"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2023-10-24_15-45-rootfs.tar.zst
# SHA256SUM=046c238e536231d90740325a32333cf9f24122f3b980a2adfd6ea1a0b2bae998
# BUILD_DATE=20231024
# BUILD_TAG=2023-10-24
# STATUS=completed
# VERSION=latest02
# END_TIME=15:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-24
begin = 2023-10-24 12:51:59.605565187+00:00
start-sync_0 = 15:10:10
start-zstd = 15:17:19
start-sync_1 = 15:43:16
end-sync_1 = 15:45:52
end = 2023-10-24 15:45:52.362272662+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
