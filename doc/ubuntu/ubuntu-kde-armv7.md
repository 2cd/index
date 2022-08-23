# ubuntu-kde-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name ubuntu-kde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-armv7 zsh
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

## ubuntu-kde-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-08-23", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_armhf_2022-08-23_01-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "44742f130fa330cc8e664e3563b4247b7cbc7584a345801357b5e3425e321827"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3949356544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1213308575

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220816"
previous_tag = "2022-08-16"
previous_file = "ubuntu-kde_armhf_2022-08-16_01-12-rootfs.tar.zst"
previous_sha256 = "68eecaf246c2adb4f46034016f1ac073f0f396446516fa2e4da42c64c50e31f7"

current_version = "latest01"
current_date = "20220823"
old_file = "ubuntu-kde_armhf_2022-08-09_01-26-rootfs.tar.zst"
old_sha256 = "7cb9e4c636d9c6c37c2a29b615e26845d0e420897bf9f398c242160bc231d8a8"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-kde_armhf_2022-08-23_01-08-rootfs.tar.zst
# SHA256SUM=44742f130fa330cc8e664e3563b4247b7cbc7584a345801357b5e3425e321827
# BUILD_DATE=20220823
# BUILD_TAG=2022-08-23
# STATUS=completed
# VERSION=latest01
# END_TIME=01:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-23
begin = 2022-08-23 00:22:41.840878415+00:00
start-sync_0 = 00:53:07
start-zstd = 00:56:07
start-sync_1 = 01:07:30
end-sync_1 = 01:08:40
end = 2022-08-23 01:08:40.940969362+00:00

[server]
repo = "cake233/ubuntu-kde-armv7"

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
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
