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
tag = ["kde", "2024-01-31"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2024-01-31_13-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d709cbf4464ba2dceda391c7f5a4fd509ef5341b9533f405fdd74eaf82f14a69"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.8G"
tar_bytes = 6123617792

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1745378824

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-kde_amd64_2023-11-22_12-58-rootfs.tar.zst"
previous_sha256 = "344b1e8ea0dd4ad627fd183060ebf0625366f33922819d40091f7ac84c20c906"

current_version = "latest01"
current_date = "20240131"
old_file = "debian-kde_amd64_2023-11-15_13-12-rootfs.tar.zst"
old_sha256 = "17717cbc2f530ef3b0d44de3906e9e57144529c851e0f6deba17e9a5f3bbd971"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2024-01-31_13-00-rootfs.tar.zst
# SHA256SUM=d709cbf4464ba2dceda391c7f5a4fd509ef5341b9533f405fdd74eaf82f14a69
# BUILD_DATE=20240131
# BUILD_TAG=2024-01-31
# STATUS=completed
# VERSION=latest01
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-31
begin = 2024-01-31 12:32:33.584225367+00:00
start-sync_0 = 12:38:26
start-zstd = 12:42:04
start-sync_1 = 12:59:06
end-sync_1 = 13:00:22
end = 2024-01-31 13:00:22.695982114+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
