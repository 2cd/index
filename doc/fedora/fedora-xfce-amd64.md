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
tag = ["xfce", "2022-10-11"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2022-10-11_13-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bb5239e4c417f5472c1a41ff75e3bf0030d3dd097acb8e013706f0fada96642b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4271793664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1425743448

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221004"
previous_tag = "2022-10-04"
previous_file = "fedora-xfce_amd64_2022-10-04_13-14-rootfs.tar.zst"
previous_sha256 = "af3c46ba4bdd035c17d461864198f35c987b9c48d6c6cd9d834a5c9429331861"

current_version = "latest02"
current_date = "20221011"
old_file = "fedora-xfce_amd64_2022-09-27_13-14-rootfs.tar.zst"
old_sha256 = "f99ddba6227717f3f73d4cae774ee5af1e9b5ad02fc80b6dc964d101bf9a19fe"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2022-10-11_13-16-rootfs.tar.zst
# SHA256SUM=bb5239e4c417f5472c1a41ff75e3bf0030d3dd097acb8e013706f0fada96642b
# BUILD_DATE=20221011
# BUILD_TAG=2022-10-11
# STATUS=completed
# VERSION=latest02
# END_TIME=13:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-11
begin = 2022-10-11 12:51:03.007158006+00:00
start-sync_0 = 12:57:21
start-zstd = 13:00:30
start-sync_1 = 13:14:43
end-sync_1 = 13:16:06
end = 2022-10-11 13:16:06.241537452+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
