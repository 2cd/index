# fedora-mate-amd64

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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2023-05-30"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2023-05-30_13-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c6553393c0a7667385e88dcf22b1a488f1e713d4aff91955e92083e0ee508415"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5170534400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1539226877

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230523"
previous_tag = "2023-05-23"
previous_file = "fedora-mate_amd64_2023-05-23_13-22-rootfs.tar.zst"
previous_sha256 = "444a453d9b3440b060644252448ab5f3500bf999db0d85f594ab9d841ffd780c"

current_version = "latest02"
current_date = "20230530"
old_file = "fedora-mate_amd64_2023-05-16_13-39-rootfs.tar.zst"
old_sha256 = "5aff519516dfec7d21b022fdf2a6984e97cc88d6dcd4ced50205e077cbaa52cc"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2023-05-30_13-31-rootfs.tar.zst
# SHA256SUM=c6553393c0a7667385e88dcf22b1a488f1e713d4aff91955e92083e0ee508415
# BUILD_DATE=20230530
# BUILD_TAG=2023-05-30
# STATUS=completed
# VERSION=latest02
# END_TIME=13:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-30
begin = 2023-05-30 12:56:53.417543162+00:00
start-sync_0 = 13:03:10
start-zstd = 13:07:13
start-sync_1 = 13:30:09
end-sync_1 = 13:31:39
end = 2023-05-30 13:31:39.419479421+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
