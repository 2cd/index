# debian-xfce-amd64

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
    --name debian-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-amd64 zsh
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

## debian-xfce-amd64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2023-07-19"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2023-07-19_12-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d1ae77ad4d33f5d7586f981ed907f922195305f40f74379a13e51b3518bcd918"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4689187840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1338102794

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230712"
previous_tag = "2023-07-12"
previous_file = "debian-xfce_amd64_2023-07-12_12-53-rootfs.tar.zst"
previous_sha256 = "b6114492398967c5723207b85cc6f849a7f5681c6667611e6d2cbadf0212db47"

current_version = "latest02"
current_date = "20230719"
old_file = "debian-xfce_amd64_2023-07-05_12-47-rootfs.tar.zst"
old_sha256 = "65b98bcfc75e61eaa59184c7539ae735998ada5c332afc7a2b38a165da4dfc79"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2023-07-19_12-55-rootfs.tar.zst
# SHA256SUM=d1ae77ad4d33f5d7586f981ed907f922195305f40f74379a13e51b3518bcd918
# BUILD_DATE=20230719
# BUILD_TAG=2023-07-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-19
begin = 2023-07-19 12:26:07.683829428+00:00
start-sync_0 = 12:32:03
start-zstd = 12:36:08
start-sync_1 = 12:53:49
end-sync_1 = 12:55:05
end = 2023-07-19 12:55:05.680782727+00:00

[server]
repo = "cake233/debian-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
