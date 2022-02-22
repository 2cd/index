# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-02-22"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-mate_arm64_2022-02-22_14-36.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "299730ed7df3325f83a8cf69970cba274de4a97edcd046366d703661905407f0"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.8G"
tar_bytes = 6192895488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1633217424

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220215"
previous_tag = "2022-02-15"
previous_file = "fedora-mate_arm64_2022-02-15_14-48-rootfs.tar.zst"
previous_sha256 = "32445d951d2fc88077878e611b527b530a7c6f6f2333983bc281b76b2786bafc"

current_version = "latest02"
current_date = "20220222"
old_file = "fedora-mate_arm64_2022-02-08_14-52-rootfs.tar.zst"
old_sha256 = "07f51b1155d0d29898780d58b87541e054f8f4a0bd8219f56bad412e61f22d85"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-02-22_14-36-rootfs.tar.zst
# SHA256SUM=299730ed7df3325f83a8cf69970cba274de4a97edcd046366d703661905407f0
# BUILD_DATE=20220222
# BUILD_TAG=2022-02-22
# STATUS=completed
# VERSION=latest02
# END_TIME=14:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-22
begin = 2022-02-22 12:48:49.321028568+00:00
start-sync_0 = 14:08:40
start-zstd = 14:15:07
start-sync_1 = 14:34:33
end-sync_1 = 14:36:21
end = 2022-02-22 14:36:21.156993026+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
