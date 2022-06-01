# debian-lxde-386

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name debian-lxde-386 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-386 zsh
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

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2022-06-01"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2022-06-01_13-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4eb52cf02b932a5daaaf526a5075caec17f9fbfc5d4aa06620e098797f84d746"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4156383232

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1187315913

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220525"
previous_tag = "2022-05-25"
previous_file = "debian-lxde_i386_2022-05-25_13-14-rootfs.tar.zst"
previous_sha256 = "453171ab984eec8decf3cc5745f377f3f62f0e4d9b3307e60bca1f2adb88a4a7"

current_version = "latest02"
current_date = "20220601"
old_file = "debian-lxde_i386_2022-05-18_13-08-rootfs.tar.zst"
old_sha256 = "2a74831bfea5f8facea82b83977c7015c32854c750fad17132aea512001e053b"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2022-06-01_13-09-rootfs.tar.zst
# SHA256SUM=4eb52cf02b932a5daaaf526a5075caec17f9fbfc5d4aa06620e098797f84d746
# BUILD_DATE=20220601
# BUILD_TAG=2022-06-01
# STATUS=completed
# VERSION=latest02
# END_TIME=13:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-01
begin = 2022-06-01 12:19:34.923355768+00:00
start-sync_0 = 12:49:43
start-zstd = 12:53:14
start-sync_1 = 13:08:35
end-sync_1 = 13:09:49
end = 2022-06-01 13:09:49.582127932+00:00

[server]
repo = "cake233/debian-lxde-386"

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
