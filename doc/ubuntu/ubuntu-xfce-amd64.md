# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-01-10", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_amd64_2023-01-10_00-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8209a87851c48618355515740b17f92cb93a8066d74fb7b8edef59de26190165"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3619732480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "944M"
zstd_bytes = 989787924

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230103"
previous_tag = "2023-01-03"
previous_file = "ubuntu-xfce_amd64_2023-01-03_00-25-rootfs.tar.zst"
previous_sha256 = "3acddfbd7b982f6ac2d347b8c6f5fece0028102b3906fe9673cc1964a4f469cb"

current_version = "latest02"
current_date = "20230110"
old_file = "ubuntu-xfce_amd64_2022-12-27_00-23-rootfs.tar.zst"
old_sha256 = "3b915debd8e3eb1448c3446bdf86246e182148f5bfb943fd3e03cd23be2436f2"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2023-01-10_00-27-rootfs.tar.zst
# SHA256SUM=8209a87851c48618355515740b17f92cb93a8066d74fb7b8edef59de26190165
# BUILD_DATE=20230110
# BUILD_TAG=2023-01-10
# STATUS=completed
# VERSION=latest02
# END_TIME=00:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-10
begin = 2023-01-10 00:03:02.553708932+00:00
start-sync_0 = 00:09:00
start-zstd = 00:11:52
start-sync_1 = 00:26:27
end-sync_1 = 00:27:28
end = 2023-01-10 00:27:28.448240487+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
