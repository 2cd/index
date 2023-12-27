# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-12-27"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2023-12-27_12-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a9f266c30a6ca4ce18319cd45aa0956700473e9c728c055fe846224818fffef7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.7G"
tar_bytes = 6057832448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1737515291

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-kde_amd64_2023-11-22_12-58-rootfs.tar.zst"
previous_sha256 = "344b1e8ea0dd4ad627fd183060ebf0625366f33922819d40091f7ac84c20c906"

current_version = "latest01"
current_date = "20231227"
old_file = "debian-kde_amd64_2023-11-15_13-12-rootfs.tar.zst"
old_sha256 = "17717cbc2f530ef3b0d44de3906e9e57144529c851e0f6deba17e9a5f3bbd971"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2023-12-27_12-58-rootfs.tar.zst
# SHA256SUM=a9f266c30a6ca4ce18319cd45aa0956700473e9c728c055fe846224818fffef7
# BUILD_DATE=20231227
# BUILD_TAG=2023-12-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-27
begin = 2023-12-27 12:31:10.677867741+00:00
start-sync_0 = 12:37:28
start-zstd = 12:40:58
start-sync_1 = 12:57:38
end-sync_1 = 12:58:53
end = 2023-12-27 12:58:53.551215678+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
