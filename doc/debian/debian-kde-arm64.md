# debian-kde-arm64

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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-11-23"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2022-11-23_13-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0c12a110a8e4e2ee28d6e901c3982e6cef1e9cccb31af0346ef97f62dae70a57"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.7G"
tar_bytes = 6095240704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1710495656

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221116"
previous_tag = "2022-11-16"
previous_file = "debian-kde_arm64_2022-11-16_13-32-rootfs.tar.zst"
previous_sha256 = "359751a801e942358a3c423dce72b8b37b68494c6b4522531d54b914a9936c5c"

current_version = "latest02"
current_date = "20221123"
old_file = "debian-kde_arm64_2022-11-09_13-25-rootfs.tar.zst"
old_sha256 = "deda5b1020c58cf6c03cba77b534934e23ecef76e810d1811b94643676e1b89d"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2022-11-23_13-27-rootfs.tar.zst
# SHA256SUM=0c12a110a8e4e2ee28d6e901c3982e6cef1e9cccb31af0346ef97f62dae70a57
# BUILD_DATE=20221123
# BUILD_TAG=2022-11-23
# STATUS=completed
# VERSION=latest02
# END_TIME=13:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-23
begin = 2022-11-23 12:18:41.699131288+00:00
start-sync_0 = 13:00:48
start-zstd = 13:06:05
start-sync_1 = 13:25:30
end-sync_1 = 13:27:05
end = 2022-11-23 13:27:05.780034169+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
