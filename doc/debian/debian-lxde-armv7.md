# debian-lxde-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name debian-lxde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2023-07-19"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-07-19_13-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "95717cce3058672e6a3159e64910432ee039d2f1c0eed8f6f94cbb40926025bc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.1G"
tar_bytes = 3273796096

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "995M"
zstd_bytes = 1043175383

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230712"
previous_tag = "2023-07-12"
previous_file = "debian-lxde_armhf_2023-07-12_12-57-rootfs.tar.zst"
previous_sha256 = "b4a9e5784474971c83ab1e554e85514733908b65cc3a73771c0bebfa4b8d9f48"

current_version = "latest02"
current_date = "20230719"
old_file = "debian-lxde_armhf_2023-07-05_12-55-rootfs.tar.zst"
old_sha256 = "110aad28594e967be652895bec958cf484a00598c0355742e81e5cfe8ba18a9b"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-07-19_13-03-rootfs.tar.zst
# SHA256SUM=95717cce3058672e6a3159e64910432ee039d2f1c0eed8f6f94cbb40926025bc
# BUILD_DATE=20230719
# BUILD_TAG=2023-07-19
# STATUS=completed
# VERSION=latest02
# END_TIME=13:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-19
begin = 2023-07-19 12:26:04.949167912+00:00
start-sync_0 = 12:49:46
start-zstd = 12:52:02
start-sync_1 = 13:02:53
end-sync_1 = 13:03:52
end = 2023-07-19 13:03:52.881895946+00:00

[server]
repo = "cake233/debian-lxde-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
