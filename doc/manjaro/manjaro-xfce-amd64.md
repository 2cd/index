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
tag = ["xfce", "2022-08-12"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2022-08-12_12-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "874befc7a7cf0b1a0c9922c258b5ee098c55812b4e57ebd5c795b925bc8d9f0e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3931316224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1168021442

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220805"
previous_tag = "2022-08-05"
previous_file = "manjaro-xfce_amd64_2022-08-05_12-51-rootfs.tar.zst"
previous_sha256 = "4b308ee8cc69051340fe92670bd64cb12a4d58a9d0bd21373ff7e8f46b74bdab"

current_version = "latest01"
current_date = "20220812"
old_file = "manjaro-xfce_amd64_2022-07-15_12-42-rootfs.tar.zst"
old_sha256 = "593854adbfcdef6dfb019da2be867c195d100343ec0bb8a2e8c0449672d80921"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2022-08-12_12-52-rootfs.tar.zst
# SHA256SUM=874befc7a7cf0b1a0c9922c258b5ee098c55812b4e57ebd5c795b925bc8d9f0e
# BUILD_DATE=20220812
# BUILD_TAG=2022-08-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-12
begin = 2022-08-12 12:28:45.810453157+00:00
start-sync_0 = 12:33:50
start-zstd = 12:37:02
start-sync_1 = 12:51:34
end-sync_1 = 12:52:45
end = 2022-08-12 12:52:45.182102595+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
