# debian-xfce-amd64

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
    --name debian-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-amd64 zsh
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

## debian-xfce-amd64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2023-05-03"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2023-05-03_12-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5f691aeee289e97bc7c2e775ad1b934393f063f3f9b31318cec95e7bcb98a494"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4164425728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1172384594

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230426"
previous_tag = "2023-04-26"
previous_file = "debian-xfce_amd64_2023-04-26_12-51-rootfs.tar.zst"
previous_sha256 = "88cb5e5470f297f2f5bcf0b36933f7f83d0147b399aa47ce45719a505183568e"

current_version = "latest01"
current_date = "20230503"
old_file = "debian-xfce_amd64_2023-04-19_12-52-rootfs.tar.zst"
old_sha256 = "47620e45ade807196b7c0a34832097be3e16cd509580bdb27a8997898d48a33c"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2023-05-03_12-48-rootfs.tar.zst
# SHA256SUM=5f691aeee289e97bc7c2e775ad1b934393f063f3f9b31318cec95e7bcb98a494
# BUILD_DATE=20230503
# BUILD_TAG=2023-05-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-03
begin = 2023-05-03 12:24:04.190284726+00:00
start-sync_0 = 12:29:37
start-zstd = 12:33:04
start-sync_1 = 12:47:08
end-sync_1 = 12:48:12
end = 2023-05-03 12:48:12.327698636+00:00

[server]
repo = "cake233/debian-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
