# ubuntu-kde-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-10-25", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2022-10-25_00-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "eeadc5c97c31eb370f14ec9623b9188d2743f79de9dc702aefb2e01a5ccc88aa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4694438400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1282254429

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221018"
previous_tag = "2022-10-18"
previous_file = "ubuntu-kde_amd64_2022-10-18_00-51-rootfs.tar.zst"
previous_sha256 = "4ab2b9ce50f9e4b0fa2930ae83c4a0c66e4b1afba2aa26a2885c9d89f9fdd585"

current_version = "latest01"
current_date = "20221025"
old_file = "ubuntu-kde_amd64_2022-10-11_00-55-rootfs.tar.zst"
old_sha256 = "8f177e23d2f2d5a6d7b527c4deb61506ce96ba87005816aedf97c0a780b02bb0"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-10-25_00-57-rootfs.tar.zst
# SHA256SUM=eeadc5c97c31eb370f14ec9623b9188d2743f79de9dc702aefb2e01a5ccc88aa
# BUILD_DATE=20221025
# BUILD_TAG=2022-10-25
# STATUS=completed
# VERSION=latest01
# END_TIME=00:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-25
begin = 2022-10-25 00:23:04.306443986+00:00
start-sync_0 = 00:30:41
start-zstd = 00:36:03
start-sync_1 = 00:55:56
end-sync_1 = 00:57:23
end = 2022-10-25 00:57:23.487977565+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
