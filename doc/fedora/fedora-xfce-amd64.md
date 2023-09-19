# fedora-xfce-amd64

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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-09-19"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2023-09-19_13-22.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7622bbf02b3c532d645a16608c7a11a88d758402a44177f40887a88c62a1e14"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4393029120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1357267631

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230912"
previous_tag = "2023-09-12"
previous_file = "fedora-xfce_amd64_2023-09-12_12-51-rootfs.tar.zst"
previous_sha256 = "ff69cb8222913e8f254ac9f39a77f7988aa158262b721d7f9837e9e87179227b"

current_version = "latest02"
current_date = "20230919"
old_file = "fedora-xfce_amd64_2023-09-05_12-51-rootfs.tar.zst"
old_sha256 = "24ef9473ed89fbcb9b94e7ec3a259ebf0ac00a709586b756a5084df31943513d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2023-09-19_13-22-rootfs.tar.zst
# SHA256SUM=a7622bbf02b3c532d645a16608c7a11a88d758402a44177f40887a88c62a1e14
# BUILD_DATE=20230919
# BUILD_TAG=2023-09-19
# STATUS=completed
# VERSION=latest02
# END_TIME=13:22

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-19
begin = 2023-09-19 12:55:35.586819875+00:00
start-sync_0 = 13:01:51
start-zstd = 13:04:53
start-sync_1 = 13:21:13
end-sync_1 = 13:22:46
end = 2023-09-19 13:22:46.837654648+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
