# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-06-16"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2023-06-16_12-43.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "28fdaa2ba3c2a1cb61bad37a044f696ccf8b734413c032178920a52a01de5562"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4087991808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1190117383

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230609"
previous_tag = "2023-06-09"
previous_file = "manjaro-xfce_amd64_2023-06-09_12-45-rootfs.tar.zst"
previous_sha256 = "5fe61a624bb45b241e83019b8917922c457eaa139393993cb994ed8fce91c71e"

current_version = "latest02"
current_date = "20230616"
old_file = "manjaro-xfce_amd64_2023-06-02_12-51-rootfs.tar.zst"
old_sha256 = "078bbe1033ec62081a2979835cb9ac41da05438ff4e9767f4741a8dc9d5fc7b6"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2023-06-16_12-43-rootfs.tar.zst
# SHA256SUM=28fdaa2ba3c2a1cb61bad37a044f696ccf8b734413c032178920a52a01de5562
# BUILD_DATE=20230616
# BUILD_TAG=2023-06-16
# STATUS=completed
# VERSION=latest02
# END_TIME=12:43

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-16
begin = 2023-06-16 12:20:29.916631257+00:00
start-sync_0 = 12:24:06
start-zstd = 12:27:07
start-sync_1 = 12:42:01
end-sync_1 = 12:43:07
end = 2023-06-16 12:43:07.229151216+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
