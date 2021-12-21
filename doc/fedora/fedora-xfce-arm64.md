# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2021-12-21"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-xfce_arm64_2021-12-21_14-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3d3927fe49a8329ab56190a6b68e30e639bd57787b6390bf7e476c8af2d6d90c"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5443841536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1490781024

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211214"
previous_tag = "2021-12-14"
previous_file = "fedora-xfce_arm64_2021-12-14_14-19-rootfs.tar.zst"
previous_sha256 = "e9d50061ef0e88fb5e7144b253542331fe7641ad59bd231dc9f6520d311bd1bc"

current_version = "latest01"
current_date = "20211221"
old_file = "fedora-xfce_arm64_2021-12-07_13-53-rootfs.tar.zst"
old_sha256 = "7ec0c391546ffd1f84088e81a279622529e679b4a190a07ffbf0e68bbb9b13e2"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2021-12-21_14-07-rootfs.tar.zst
# SHA256SUM=3d3927fe49a8329ab56190a6b68e30e639bd57787b6390bf7e476c8af2d6d90c
# BUILD_DATE=20211221
# BUILD_TAG=2021-12-21
# STATUS=completed
# VERSION=latest01
# END_TIME=14:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-21
begin = 2021-12-21 12:49:11.307315714+00:00
start-sync_0 = 13:47:11
start-zstd = 13:51:41
start-sync_1 = 14:05:47
end-sync_1 = 14:07:13
end = 2021-12-21 14:07:13.696012660+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
