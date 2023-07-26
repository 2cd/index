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
tag = ["kde", "2023-07-26"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2023-07-26_13-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aeb3213d68809c092b571d8d5d67bd79957bf817e2cd3f9402b26db33d61a6aa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.9G"
tar_bytes = 6330242048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1854556768

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230719"
previous_tag = "2023-07-19"
previous_file = "debian-kde_amd64_2023-07-19_13-07-rootfs.tar.zst"
previous_sha256 = "247ce3f5c5d2877c79a00b4a3d4dec983a04979898b6151ba66a4ac28c2ea346"

current_version = "latest01"
current_date = "20230726"
old_file = "debian-kde_amd64_2023-07-12_12-56-rootfs.tar.zst"
old_sha256 = "c346f071ed839a4a167ee3e83ad308f41a79c2ec9e87378a40372296a073ece3"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2023-07-26_13-07-rootfs.tar.zst
# SHA256SUM=aeb3213d68809c092b571d8d5d67bd79957bf817e2cd3f9402b26db33d61a6aa
# BUILD_DATE=20230726
# BUILD_TAG=2023-07-26
# STATUS=completed
# VERSION=latest01
# END_TIME=13:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-26
begin = 2023-07-26 12:22:20.430794554+00:00
start-sync_0 = 12:30:22
start-zstd = 12:37:34
start-sync_1 = 13:05:01
end-sync_1 = 13:07:11
end = 2023-07-26 13:07:11.081709082+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
