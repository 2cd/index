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
tag = ["mate", "2022-08-24"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-mate_amd64_2022-08-24_12-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ca3401956b4171cfdb4e637fbd7a24eda03c041c288c3ea4b6157b69918c4fc8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3985191424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1094553562

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220817"
previous_tag = "2022-08-17"
previous_file = "debian-mate_amd64_2022-08-17_12-46-rootfs.tar.zst"
previous_sha256 = "f41d9ec7ef8ee944b7b5ca720e0eca64e2f53bf84ea5eff455cd1e4a2c42903c"

current_version = "latest01"
current_date = "20220824"
old_file = "debian-mate_amd64_2022-08-10_12-45-rootfs.tar.zst"
old_sha256 = "106eea0447f9d45eabc30ad06dad338fe6d820e1cbaa746ab989cd38c37d3851"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-mate_amd64_2022-08-24_12-50-rootfs.tar.zst
# SHA256SUM=ca3401956b4171cfdb4e637fbd7a24eda03c041c288c3ea4b6157b69918c4fc8
# BUILD_DATE=20220824
# BUILD_TAG=2022-08-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-24
begin = 2022-08-24 12:22:31.218649264+00:00
start-sync_0 = 12:29:58
start-zstd = 12:34:01
start-sync_1 = 12:49:20
end-sync_1 = 12:50:39
end = 2022-08-24 12:50:39.700781084+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
