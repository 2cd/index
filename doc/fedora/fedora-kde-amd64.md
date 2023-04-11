# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-04-11"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-04-11_13-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "10d5f9e93b129fed6ce62840ebac43c8ace1e520853d0f3d160f392350a666d9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5341203456

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1720954712

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230404"
previous_tag = "2023-04-04"
previous_file = "fedora-kde_amd64_2023-04-04_13-28-rootfs.tar.zst"
previous_sha256 = "4b9c2e7ace43f430283819af571138cb57247beb287b5b20d03873eb9ec516e0"

current_version = "latest02"
current_date = "20230411"
old_file = "fedora-kde_amd64_2023-03-28_13-45-rootfs.tar.zst"
old_sha256 = "6e22995cbcf265e421fec8d8b7c747638855018c8b8a1a8d612fab0164887344"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-04-11_13-31-rootfs.tar.zst
# SHA256SUM=10d5f9e93b129fed6ce62840ebac43c8ace1e520853d0f3d160f392350a666d9
# BUILD_DATE=20230411
# BUILD_TAG=2023-04-11
# STATUS=completed
# VERSION=latest02
# END_TIME=13:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-11
begin = 2023-04-11 12:58:54.620324064+00:00
start-sync_0 = 13:05:39
start-zstd = 13:09:43
start-sync_1 = 13:30:06
end-sync_1 = 13:31:50
end = 2023-04-11 13:31:50.502369245+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
