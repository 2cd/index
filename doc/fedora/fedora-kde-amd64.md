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
tag = ["kde", "2023-03-21"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-03-21_13-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1223d6d5d2d40fd203cc891e9dedaacb01d74de2190d56726fabb12db14d6dab"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5501857280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1770389664

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230314"
previous_tag = "2023-03-14"
previous_file = "fedora-kde_amd64_2023-03-14_13-25-rootfs.tar.zst"
previous_sha256 = "43936dd22f3cbb66c07e8d8139af2f054e91b118b5d1d449d0738bb85107d618"

current_version = "latest01"
current_date = "20230321"
old_file = "fedora-kde_amd64_2023-03-07_13-35-rootfs.tar.zst"
old_sha256 = "3a3e87fc144c8d7a118b38071229ab0ea48db6588619f045019ce5e7c70008f7"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-03-21_13-34-rootfs.tar.zst
# SHA256SUM=1223d6d5d2d40fd203cc891e9dedaacb01d74de2190d56726fabb12db14d6dab
# BUILD_DATE=20230321
# BUILD_TAG=2023-03-21
# STATUS=completed
# VERSION=latest01
# END_TIME=13:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-21
begin = 2023-03-21 13:02:39.411746277+00:00
start-sync_0 = 13:09:08
start-zstd = 13:13:16
start-sync_1 = 13:32:15
end-sync_1 = 13:34:01
end = 2023-03-21 13:34:01.545343333+00:00

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
