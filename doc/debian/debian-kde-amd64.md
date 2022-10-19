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
tag = ["kde", "2022-10-19"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2022-10-19_12-57.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f956d29aed8fb4c54cf6c087b1b02d6747dfb7c7016a617d033d4863525a8d01"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5304888320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1527624638

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221012"
previous_tag = "2022-10-12"
previous_file = "debian-kde_amd64_2022-10-12_13-01-rootfs.tar.zst"
previous_sha256 = "5e45bd13eba13a43c92ceecb884fb711525016e3e24d98e4487c7127a996f722"

current_version = "latest01"
current_date = "20221019"
old_file = "debian-kde_amd64_2022-10-05_12-54-rootfs.tar.zst"
old_sha256 = "d50a78f566e7f82e2ef7d443c804eecb2f97db0c2fc3e51f31234847e24a1798"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-10-19_12-57-rootfs.tar.zst
# SHA256SUM=f956d29aed8fb4c54cf6c087b1b02d6747dfb7c7016a617d033d4863525a8d01
# BUILD_DATE=20221019
# BUILD_TAG=2022-10-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-19
begin = 2022-10-19 12:17:20.345611642+00:00
start-sync_0 = 12:26:00
start-zstd = 12:32:06
start-sync_1 = 12:55:43
end-sync_1 = 12:57:19
end = 2022-10-19 12:57:19.807801860+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
zsh = ''

[port]
tcp = [5902, 36080]
```
