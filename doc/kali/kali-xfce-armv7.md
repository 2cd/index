# kali-xfce-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name kali-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-armv7 zsh
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

## kali-xfce-armv7.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-05-19"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2022-05-19_13-36.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d2d16de4bb85f857adc3f64e2c49fa7c78e704d1a07bb46fc4138d213b41c745"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4817495040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1522779393

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220512"
previous_tag = "2022-05-12"
previous_file = "kali-xfce_armhf_2022-05-12_13-28-rootfs.tar.zst"
previous_sha256 = "93a42a77a11b8e10d0e675c911a37f3b8dba9fd47ced06e95b73a5a5cc9e46d7"

current_version = "latest01"
current_date = "20220519"
old_file = "kali-xfce_armhf_2022-04-28_13-36-rootfs.tar.zst"
old_sha256 = "2b915810cce1121560515170d3ad1e7063d6a56bfe6a1ace808c8e4e0e97113b"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2022-05-19_13-36-rootfs.tar.zst
# SHA256SUM=d2d16de4bb85f857adc3f64e2c49fa7c78e704d1a07bb46fc4138d213b41c745
# BUILD_DATE=20220519
# BUILD_TAG=2022-05-19
# STATUS=completed
# VERSION=latest01
# END_TIME=13:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-19
begin = 2022-05-19 12:18:51.258047202+00:00
start-sync_0 = 13:11:41
start-zstd = 13:17:03
start-sync_1 = 13:34:28
end-sync_1 = 13:36:23
end = 2022-05-19 13:36:23.453857171+00:00

[server]
repo = "cake233/kali-xfce-armv7"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
