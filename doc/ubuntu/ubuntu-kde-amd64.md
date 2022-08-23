# ubuntu-kde-amd64

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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-08-23", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2022-08-23_00-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7ca04a1e09a9d6760fbd12fa32626720a494a7b6a8c42bc28aa1363d50def06b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4675574784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1279317587

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220816"
previous_tag = "2022-08-16"
previous_file = "ubuntu-kde_amd64_2022-08-16_00-52-rootfs.tar.zst"
previous_sha256 = "908fc23c1862a4c2c5e11aca61628705a8383d7f58604948e2d821710185534a"

current_version = "latest02"
current_date = "20220823"
old_file = "ubuntu-kde_amd64_2022-08-09_00-54-rootfs.tar.zst"
old_sha256 = "cd4c0d2cf10ec064e6184ed29e7137e1bb26fdf2c263858dbd69fa38fdd1253a"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-08-23_00-49-rootfs.tar.zst
# SHA256SUM=7ca04a1e09a9d6760fbd12fa32626720a494a7b6a8c42bc28aa1363d50def06b
# BUILD_DATE=20220823
# BUILD_TAG=2022-08-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-23
begin = 2022-08-23 00:22:42.658307481+00:00
start-sync_0 = 00:29:06
start-zstd = 00:33:19
start-sync_1 = 00:48:29
end-sync_1 = 00:49:42
end = 2022-08-23 00:49:42.893960512+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
