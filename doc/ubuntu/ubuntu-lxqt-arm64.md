# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-05-16", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-05-16_00-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "29daf606a63ad8e4e1ca3b9d5be81a226d4e8cfbd3d502b31215f43ba5b01885"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4250737664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1151411979

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230509"
previous_tag = "2023-05-09"
previous_file = "ubuntu-lxqt_arm64_2023-05-09_00-55-rootfs.tar.zst"
previous_sha256 = "4959ae1c78095653fbdde80024a26dbd35358f2ade99e5efa6dc95789a3966a9"

current_version = "latest02"
current_date = "20230516"
old_file = "ubuntu-lxqt_arm64_2023-05-02_00-58-rootfs.tar.zst"
old_sha256 = "4002bcbb82f2296493629b8e2de9b23c2b89efd7817df36e7f44caea7dd082c9"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-05-16_00-55-rootfs.tar.zst
# SHA256SUM=29daf606a63ad8e4e1ca3b9d5be81a226d4e8cfbd3d502b31215f43ba5b01885
# BUILD_DATE=20230516
# BUILD_TAG=2023-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=00:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-16
begin = 2023-05-16 00:03:08.828056525+00:00
start-sync_0 = 00:36:12
start-zstd = 00:39:30
start-sync_1 = 00:54:09
end-sync_1 = 00:55:14
end = 2023-05-16 00:55:14.433822945+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
