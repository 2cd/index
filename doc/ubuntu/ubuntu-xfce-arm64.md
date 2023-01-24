# ubuntu-xfce-arm64

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
    --name ubuntu-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-arm64 zsh
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

## ubuntu-xfce-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2023-01-24", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-xfce_arm64_2023-01-24_00-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c0d635928c47403bdc502657f8fc1c6edb8e3095f0b505dbdd77d4f53e0e822a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3888428032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1010M"
zstd_bytes = 1058301758

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230117"
previous_tag = "2023-01-17"
previous_file = "ubuntu-xfce_arm64_2023-01-17_00-49-rootfs.tar.zst"
previous_sha256 = "ec4e43af9511e7c43e4b60dab9402c8c08280aeb71674eeae3c8162214e12db1"

current_version = "latest01"
current_date = "20230124"
old_file = "ubuntu-xfce_arm64_2023-01-10_00-51-rootfs.tar.zst"
old_sha256 = "2a9d28dca8699e9e9705338703afa530eaa720c67120b662c04411f463b2377f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-xfce_arm64_2023-01-24_00-49-rootfs.tar.zst
# SHA256SUM=c0d635928c47403bdc502657f8fc1c6edb8e3095f0b505dbdd77d4f53e0e822a
# BUILD_DATE=20230124
# BUILD_TAG=2023-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=00:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-24
begin = 2023-01-24 00:03:04.118864564+00:00
start-sync_0 = 00:32:33
start-zstd = 00:35:24
start-sync_1 = 00:49:00
end-sync_1 = 00:49:59
end = 2023-01-24 00:49:59.663020377+00:00

[server]
repo = "cake233/ubuntu-xfce-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
