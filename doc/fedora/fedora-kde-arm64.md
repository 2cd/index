# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2022-10-04"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2022-10-04_14-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a94bd31320947f2a45d983a38789013075c9af9176ed041deb227022644bc68b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.8G"
tar_bytes = 7208383488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1927828489

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220927"
previous_tag = "2022-09-27"
previous_file = "fedora-kde_arm64_2022-09-27_14-38-rootfs.tar.zst"
previous_sha256 = "8745de4aa0b7964f2b2a40880b0c17622ec7b1131e59f0b7e34bfe88ecebef0a"

current_version = "latest01"
current_date = "20221004"
old_file = "fedora-kde_arm64_2022-09-20_15-05-rootfs.tar.zst"
old_sha256 = "3c3cd9cefe85e3fd74345ae54c91212952ed8e763adecc2fdbc67bf953cd7b61"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2022-10-04_14-48-rootfs.tar.zst
# SHA256SUM=a94bd31320947f2a45d983a38789013075c9af9176ed041deb227022644bc68b
# BUILD_DATE=20221004
# BUILD_TAG=2022-10-04
# STATUS=completed
# VERSION=latest01
# END_TIME=14:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-04
begin = 2022-10-04 12:49:37.711755082+00:00
start-sync_0 = 14:16:48
start-zstd = 14:23:36
start-sync_1 = 14:45:08
end-sync_1 = 14:48:55
end = 2022-10-04 14:48:55.840077413+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
