# arch-xfce-amd64

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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-amd64 zsh
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

## arch-xfce-amd64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-10-12"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_amd64_2022-10-12_00-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6b67083ab14bc455e8a0dedf1ed872ba9616aa6033f987896af551cd44a49cec"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3807862272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1135955110

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221005"
previous_tag = "2022-10-05"
previous_file = "arch-xfce_amd64_2022-10-05_00-56-rootfs.tar.zst"
previous_sha256 = "008a11c2ae1a89e594486d23edbc05381571621f029e9a630d4e90c1446709b4"

current_version = "latest02"
current_date = "20221012"
old_file = "arch-xfce_amd64_2022-09-28_00-58-rootfs.tar.zst"
old_sha256 = "c5add55bb11121d02dfbfc794d3de588d468501bb2629483548a1f0d309379c9"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2022-10-12_00-57-rootfs.tar.zst
# SHA256SUM=6b67083ab14bc455e8a0dedf1ed872ba9616aa6033f987896af551cd44a49cec
# BUILD_DATE=20221012
# BUILD_TAG=2022-10-12
# STATUS=completed
# VERSION=latest02
# END_TIME=00:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-12
begin = 2022-10-12 00:33:28.937296449+00:00
start-sync_0 = 00:37:45
start-zstd = 00:40:55
start-sync_1 = 00:55:58
end-sync_1 = 00:57:04
end = 2022-10-12 00:57:04.222568869+00:00

[server]
repo = "cake233/arch-xfce-amd64"

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
