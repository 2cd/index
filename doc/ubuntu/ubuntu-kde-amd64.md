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
tag = ["kde", "2023-03-21", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2023-03-21_00-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "00c1e868dec54ace033990f402ff1177fa7b7325e37d5d2e72e424419092f7ba"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4776153600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1320031882

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230314"
previous_tag = "2023-03-14"
previous_file = "ubuntu-kde_amd64_2023-03-14_00-36-rootfs.tar.zst"
previous_sha256 = "9f6eddc8ef9718748e696647324665425c870fe98ed3cf161b44274b2bd4c605"

current_version = "latest02"
current_date = "20230321"
old_file = "ubuntu-kde_amd64_2023-03-07_00-34-rootfs.tar.zst"
old_sha256 = "4fb7ce3d13c1c9b0454ea1578db1592229bd7dfd97fee94e153f320c91622439"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2023-03-21_00-42-rootfs.tar.zst
# SHA256SUM=00c1e868dec54ace033990f402ff1177fa7b7325e37d5d2e72e424419092f7ba
# BUILD_DATE=20230321
# BUILD_TAG=2023-03-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-21
begin = 2023-03-21 00:03:10.539957573+00:00
start-sync_0 = 00:12:58
start-zstd = 00:18:58
start-sync_1 = 00:40:35
end-sync_1 = 00:42:04
end = 2023-03-21 00:42:04.980994112+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
