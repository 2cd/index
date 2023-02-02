# kali-xfce-amd64

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
    --name kali-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-amd64 zsh
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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-02-02"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2023-02-02_13-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5835161c6d2a6b83fe295c9a28b28d349e8e789d19d8aaf2c49347ba7925d3b9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4396692992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1241704928

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230126"
previous_tag = "2023-01-26"
previous_file = "kali-xfce_amd64_2023-01-26_12-55-rootfs.tar.zst"
previous_sha256 = "3cced2db7c6d56859cc1863652771576f128084c133c0f8b0417c366d92cd4de"

current_version = "latest01"
current_date = "20230202"
old_file = "kali-xfce_amd64_2023-01-19_12-57-rootfs.tar.zst"
old_sha256 = "b87840a85daff7b6ab2908eaf2457f831e6c5653b92c00796964b128ebe7def6"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2023-02-02_13-00-rootfs.tar.zst
# SHA256SUM=5835161c6d2a6b83fe295c9a28b28d349e8e789d19d8aaf2c49347ba7925d3b9
# BUILD_DATE=20230202
# BUILD_TAG=2023-02-02
# STATUS=completed
# VERSION=latest01
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-02
begin = 2023-02-02 12:28:16.343900869+00:00
start-sync_0 = 12:37:09
start-zstd = 12:41:24
start-sync_1 = 12:58:52
end-sync_1 = 13:00:14
end = 2023-02-02 13:00:14.582530144+00:00

[server]
repo = "cake233/kali-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
