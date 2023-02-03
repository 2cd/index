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
tag = ["xfce", "2023-02-03"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-02-03_12-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "45e6ea107e8e27ed4741fbefedf7b7e0d8d184a6d8673236f52f0506c09fb3e6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4536650752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1305096638

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230127"
previous_tag = "2023-01-27"
previous_file = "manjaro-xfce_arm64_2023-01-27_12-53-rootfs.tar.zst"
previous_sha256 = "717b46d1cb4fa7f5db4bbaf855d84b6bf5beef41d94d2ac8f66b5c9b62542cf7"

current_version = "latest01"
current_date = "20230203"
old_file = "manjaro-xfce_arm64_2023-01-20_12-55-rootfs.tar.zst"
old_sha256 = "e8264f74ea3ea4d4de4ef1d29cc8d1525f566702c264cb7ddaaf324996bd59cc"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-02-03_12-53-rootfs.tar.zst
# SHA256SUM=45e6ea107e8e27ed4741fbefedf7b7e0d8d184a6d8673236f52f0506c09fb3e6
# BUILD_DATE=20230203
# BUILD_TAG=2023-02-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-03
begin = 2023-02-03 12:20:00.564038007+00:00
start-sync_0 = 12:33:51
start-zstd = 12:37:23
start-sync_1 = 12:51:55
end-sync_1 = 12:53:09
end = 2023-02-03 12:53:09.403400049+00:00

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
