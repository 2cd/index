# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2021-12-08"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "debian-xfce_arm64_2021-12-08_13-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f4c63384ac067c4cf489e816866ecfa761bedf6e22e3c409a25225d8015836b2"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4193113600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1164371579

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211201"
previous_tag = "2021-12-01"
previous_file = "debian-xfce_arm64_2021-12-01_13-24-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest01"
current_date = "20211208"
old_file = "debian-xfce-arm64_2021-11-28_22-41-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2021-12-08_13-10-rootfs.tar.zst
# SHA256SUM=f4c63384ac067c4cf489e816866ecfa761bedf6e22e3c409a25225d8015836b2
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=13:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 12:19:52.061583488+00:00
start-sync_0 = 12:54:43
start-zstd = 12:58:15
start-sync_1 = 13:09:32
end-sync_1 = 13:10:48
end = 2021-12-08 13:10:48.624241836+00:00

[server]
repo = "cake233/debian-xfce-arm64"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
