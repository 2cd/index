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
tag = ["mate", "2023-08-30"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_amd64_2023-08-30_12-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "44829d856db75854ae29d941c0d588d4108eabe052e03322352653072dcde545"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4189917696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1140265985

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230823"
previous_tag = "2023-08-23"
previous_file = "debian-mate_amd64_2023-08-23_12-46-rootfs.tar.zst"
previous_sha256 = "7794050ef5f00e7001b92981e6d75a5f5b5b91e1cb4e2ff0ee915ad4f4243fa5"

current_version = "latest02"
current_date = "20230830"
old_file = "debian-mate_amd64_2023-08-16_12-50-rootfs.tar.zst"
old_sha256 = "70f3ee9c6c6f3bb8f3338efed9fce64af50ffa4f9faccd3253cf37190a3df4a3"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2023-08-30_12-50-rootfs.tar.zst
# SHA256SUM=44829d856db75854ae29d941c0d588d4108eabe052e03322352653072dcde545
# BUILD_DATE=20230830
# BUILD_TAG=2023-08-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-30
begin = 2023-08-30 12:25:13.169012884+00:00
start-sync_0 = 12:31:10
start-zstd = 12:34:39
start-sync_1 = 12:49:00
end-sync_1 = 12:50:12
end = 2023-08-30 12:50:12.408003954+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```