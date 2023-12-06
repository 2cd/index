# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2023-12-06"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-12-06_14-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "276e4c98408ef05ea10b7d1feae1064ac196c45c7fbdf6facc7a38eac0fa3099"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4992309760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1329725991

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-xfce_arm64_2023-11-22_13-52-rootfs.tar.zst"
previous_sha256 = "637a5d80c302a0549389f503aa709cd1516b9c20962ce81c15f00f12b2d9a23f"

current_version = "latest01"
current_date = "20231206"
old_file = "debian-xfce_arm64_2023-11-15_13-54-rootfs.tar.zst"
old_sha256 = "ebaa5dc9bc169cbfb68862b46781cf25de9b725890984b6a8bf06b1c9d4d4380"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-12-06_14-01-rootfs.tar.zst
# SHA256SUM=276e4c98408ef05ea10b7d1feae1064ac196c45c7fbdf6facc7a38eac0fa3099
# BUILD_DATE=20231206
# BUILD_TAG=2023-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=14:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-06
begin = 2023-12-06 12:33:15.054155164+00:00
start-sync_0 = 13:44:47
start-zstd = 13:47:20
start-sync_1 = 14:00:49
end-sync_1 = 14:01:46
end = 2023-12-06 14:01:46.502475818+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
