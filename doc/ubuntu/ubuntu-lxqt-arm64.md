# ubuntu-lxqt-arm64

## How to run it?

```shell
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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it ubuntu-lxqt-arm64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2021-12-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_arm64_2021-12-07_01-45.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "052719895a94bafb464380185ff5dce0dc4c3e154af7d5a555593e0fea9688ab"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3823355392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "954M"
zstd_bytes = 999598004

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211130"
last_tag = "2021-11-30"
last_file = "ubuntu-lxqt_arm64_2021-11-30_15-05-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest02"
current_date = "20211207"
old_file = "ubuntu-lxqt-arm64_2021-11-28_22-31-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2021-12-07_01-45-rootfs.tar.zst
# SHA256SUM=052719895a94bafb464380185ff5dce0dc4c3e154af7d5a555593e0fea9688ab
# BUILD_DATE=20211207
# BUILD_TAG=2021-12-07
# STATUS=completed
# VERSION=latest02
# END_TIME=01:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-07
begin = 2021-12-07 00:23:05.662300288+00:00
start-sync_0 = 01:31:03
start-zstd = 01:34:17
start-sync_1 = 01:44:55
end-sync_1 = 01:45:56
end = 2021-12-07 01:45:56.680839726+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"

[version]
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
