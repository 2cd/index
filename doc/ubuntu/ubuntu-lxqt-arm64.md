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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2022-02-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "ubuntu-lxqt_arm64_2022-02-01_01-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4411d17aba9db5aed8adb7ec120d84b117921fe1759d5863505e2b087e771544"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3840945152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "960M"
zstd_bytes = 1006579998

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220125"
previous_tag = "2022-01-25"
previous_file = "ubuntu-lxqt_arm64_2022-01-25_01-07-rootfs.tar.zst"
previous_sha256 = "c2419bedb51f2e08084e540e817732617d150e47510c0ed60ab5750c2c177582"

current_version = "latest02"
current_date = "20220201"
old_file = "ubuntu-lxqt_arm64_2022-01-18_01-14-rootfs.tar.zst"
old_sha256 = "5ecf2f74945313def78650bc0d93686d1f1e7360e053b61594131871cc2b8d3b"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2022-02-01_01-12-rootfs.tar.zst
# SHA256SUM=4411d17aba9db5aed8adb7ec120d84b117921fe1759d5863505e2b087e771544
# BUILD_DATE=20220201
# BUILD_TAG=2022-02-01
# STATUS=completed
# VERSION=latest02
# END_TIME=01:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-01
begin = 2022-02-01 00:27:23.610631569+00:00
start-sync_0 = 00:58:20
start-zstd = 01:01:37
start-sync_1 = 01:11:13
end-sync_1 = 01:12:19
end = 2022-02-01 01:12:19.689553531+00:00

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
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
