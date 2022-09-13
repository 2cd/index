# ubuntu-kde-arm64

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
    --name ubuntu-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-arm64 zsh
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

## ubuntu-kde-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-09-13", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_arm64_2022-09-13_01-25.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e8cb8ceae220cb422112f3b846291333b731d0f9589ee13bd2d674e528bc071f"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 4980305920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1361727946

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220906"
previous_tag = "2022-09-06"
previous_file = "ubuntu-kde_arm64_2022-09-06_01-40-rootfs.tar.zst"
previous_sha256 = "2746845a654392a1504a3089299d8e6adf4cef100097f10261d760dfcb57e047"

current_version = "latest01"
current_date = "20220913"
old_file = "ubuntu-kde_arm64_2022-08-30_01-21-rootfs.tar.zst"
old_sha256 = "6d04c394115979be751a1a8c1383c5eca54f31cdaddb81af5db0de061bdd5ff5"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kde_arm64_2022-09-13_01-25-rootfs.tar.zst
# SHA256SUM=e8cb8ceae220cb422112f3b846291333b731d0f9589ee13bd2d674e528bc071f
# BUILD_DATE=20220913
# BUILD_TAG=2022-09-13
# STATUS=completed
# VERSION=latest01
# END_TIME=01:25

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-13
begin = 2022-09-13 00:24:57.981591363+00:00
start-sync_0 = 01:01:16
start-zstd = 01:05:36
start-sync_1 = 01:22:15
end-sync_1 = 01:25:55
end = 2022-09-13 01:25:55.793526908+00:00

[server]
repo = "cake233/ubuntu-kde-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu2) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
