# debian-mate-amd64

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
    --name debian-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-mate-amd64 zsh
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

## debian-mate-amd64.toml

```toml
[main]
name = "debian"
tag = ["mate", "2024-01-10"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_amd64_2024-01-10_12-38.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6b7e05b4278cab87dbb48dcbd8e3f521e51c3d065eaf79b1fa4d9331ecd4f088"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3789975552

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "989M"
zstd_bytes = 1036958951

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-mate_amd64_2023-11-22_12-49-rootfs.tar.zst"
previous_sha256 = "bc9998abddaa2535a1cb878dd23dd4ac4eb353046c80d110f33714de11749216"

current_version = "latest02"
current_date = "20240110"
old_file = "debian-mate_amd64_2023-11-15_12-50-rootfs.tar.zst"
old_sha256 = "0f5c1a7225fc1ba7192e7eab68ec52a8b57f933f3bb29a9b2ccf1fc397424c86"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2024-01-10_12-38-rootfs.tar.zst
# SHA256SUM=6b7e05b4278cab87dbb48dcbd8e3f521e51c3d065eaf79b1fa4d9331ecd4f088
# BUILD_DATE=20240110
# BUILD_TAG=2024-01-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-10
begin = 2024-01-10 12:22:11.516697217+00:00
start-sync_0 = 12:25:50
start-zstd = 12:27:54
start-sync_1 = 12:37:28
end-sync_1 = 12:38:12
end = 2024-01-10 12:38:12.974628654+00:00

[server]
repo = "cake233/debian-mate-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = ''

[port]
tcp = [5902, 36080]
```
