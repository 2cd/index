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
tag = ["xfce", "2023-08-22"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2023-08-22_12-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "595e17c8fd1c111d58794bfc4390a7c1b863ef9c07208c03bdcffe01d81b5664"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3229953024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "768M"
zstd_bytes = 805045312

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230815"
previous_tag = "2023-08-15"
previous_file = "fedora-xfce_amd64_2023-08-15_12-36-rootfs.tar.zst"
previous_sha256 = "dcc27ff215e29efbc32e3df446a7ec607812c464d1197fc4eceea83316a96b53"

current_version = "latest01"
current_date = "20230822"
old_file = "fedora-xfce_amd64_2023-08-08_13-02-rootfs.tar.zst"
old_sha256 = "f70833674548042ec579207d7b15754b3a2caede7db4520ad47176ad029b84ef"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2023-08-22_12-32-rootfs.tar.zst
# SHA256SUM=595e17c8fd1c111d58794bfc4390a7c1b863ef9c07208c03bdcffe01d81b5664
# BUILD_DATE=20230822
# BUILD_TAG=2023-08-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-22
begin = 2023-08-22 12:13:34.522287594+00:00
start-sync_0 = 12:18:01
start-zstd = 12:20:11
start-sync_1 = 12:31:39
end-sync_1 = 12:32:39
end = 2023-08-22 12:32:39.115873933+00:00

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
