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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-01-11", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-kde_amd64_2022-01-11_00-44.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "43ce2d821f72a0eda1e20f6eb0c15671fa2ff7d5791f7eea678757087dae1110"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3891059712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1114367002

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220104"
previous_tag = "2022-01-04"
previous_file = "ubuntu-kde_amd64_2022-01-04_00-50-rootfs.tar.zst"
previous_sha256 = "392171dad61e09291bf6c4228ef371ce94dd5fc86209884f2ae117ac4fb5cebf"

current_version = "latest01"
current_date = "20220111"
old_file = "ubuntu-kde_amd64_2021-12-28_00-43-rootfs.tar.zst"
old_sha256 = "45bcc18211d6cbbd6eb6ae46dbd478cd3df666d0b87c03da8e2cb5f6b163ac71"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-01-11_00-44-rootfs.tar.zst
# SHA256SUM=43ce2d821f72a0eda1e20f6eb0c15671fa2ff7d5791f7eea678757087dae1110
# BUILD_DATE=20220111
# BUILD_TAG=2022-01-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-11
begin = 2022-01-11 00:23:05.671079510+00:00
start-sync_0 = 00:29:02
start-zstd = 00:32:27
start-sync_1 = 00:42:57
end-sync_1 = 00:44:05
end = 2022-01-11 00:44:05.329814219+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
