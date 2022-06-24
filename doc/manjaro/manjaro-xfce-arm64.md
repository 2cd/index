# manjaro-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-06-24"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2022-06-24_12-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "59f875a51a9d9645d6fc3dcde1ff54ca2cd6c023f72cbacb5ed84bbc5b04bdfb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4444983808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1272179593

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220617"
previous_tag = "2022-06-17"
previous_file = "manjaro-xfce_arm64_2022-06-17_13-00-rootfs.tar.zst"
previous_sha256 = "75381503c28d7dcecf801457201f13c1bc4fd23f8f1cba046874f1b2422be1a0"

current_version = "latest02"
current_date = "20220624"
old_file = "manjaro-xfce_arm64_2022-06-10_12-51-rootfs.tar.zst"
old_sha256 = "f0a3e15246cd0d3edcfec4ba7017de242ce37e5b62f52ad27d57e8a720971f9c"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2022-06-24_12-55-rootfs.tar.zst
# SHA256SUM=59f875a51a9d9645d6fc3dcde1ff54ca2cd6c023f72cbacb5ed84bbc5b04bdfb
# BUILD_DATE=20220624
# BUILD_TAG=2022-06-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-24
begin = 2022-06-24 12:20:36.727087608+00:00
start-sync_0 = 12:34:12
start-zstd = 12:38:00
start-sync_1 = 12:54:06
end-sync_1 = 12:55:23
end = 2022-06-24 12:55:23.872738666+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
