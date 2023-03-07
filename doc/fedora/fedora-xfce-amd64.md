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
tag = ["xfce", "2023-03-07"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2023-03-07_13-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1aeaba9b749bc2a66c0ca28405dd5e37ebc8a8eadc1428eb503b5eeec90faa70"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4343989248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1389040508

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230228"
previous_tag = "2023-02-28"
previous_file = "fedora-xfce_amd64_2023-02-28_13-29-rootfs.tar.zst"
previous_sha256 = "ed99eb7ec089593460f098cc201f21b4a5df91ab57287f1a4eb34fb9d7f5372a"

current_version = "latest02"
current_date = "20230307"
old_file = "fedora-xfce_amd64_2023-02-21_13-30-rootfs.tar.zst"
old_sha256 = "21eee97a75a1415f3dd1536b2baeddb4a169384c2f558b79d2e9a361ff1878a6"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2023-03-07_13-31-rootfs.tar.zst
# SHA256SUM=1aeaba9b749bc2a66c0ca28405dd5e37ebc8a8eadc1428eb503b5eeec90faa70
# BUILD_DATE=20230307
# BUILD_TAG=2023-03-07
# STATUS=completed
# VERSION=latest02
# END_TIME=13:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-07
begin = 2023-03-07 13:05:18.101938742+00:00
start-sync_0 = 13:12:11
start-zstd = 13:15:20
start-sync_1 = 13:30:08
end-sync_1 = 13:31:29
end = 2023-03-07 13:31:29.478709318+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
