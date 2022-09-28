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
tag = ["kde", "2022-09-28"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2022-09-28_12-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c092d1fa341dd0cdb536fd4ac7a396618188b9163e20b31c62cb5732d3655b20"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5457469952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1560834191

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220921"
previous_tag = "2022-09-21"
previous_file = "debian-kde_amd64_2022-09-21_12-49-rootfs.tar.zst"
previous_sha256 = "8707a7ddad842a6d8b695fb64ae5a4190d7ff98a1e9c730d055be641c5f49d04"

current_version = "latest02"
current_date = "20220928"
old_file = "debian-kde_amd64_2022-09-14_12-50-rootfs.tar.zst"
old_sha256 = "df5b37f8f4fa916529d81252ba47c377429bd10d1f017380f2e77814ea831b31"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-09-28_12-54-rootfs.tar.zst
# SHA256SUM=c092d1fa341dd0cdb536fd4ac7a396618188b9163e20b31c62cb5732d3655b20
# BUILD_DATE=20220928
# BUILD_TAG=2022-09-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-28
begin = 2022-09-28 12:21:07.220601659+00:00
start-sync_0 = 12:27:53
start-zstd = 12:32:43
start-sync_1 = 12:52:49
end-sync_1 = 12:54:21
end = 2022-09-28 12:54:21.137229636+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-1) 2.35'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
