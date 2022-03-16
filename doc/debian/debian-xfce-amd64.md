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
tag = ["xfce", "2022-03-16"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-xfce_amd64_2022-03-16_12-47.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "805da933c7a3620fa2d32079bfd0ffd7a546f991277225d746dacee5039b573f"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3830700544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1096734911

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220309"
previous_tag = "2022-03-09"
previous_file = "debian-xfce_amd64_2022-03-09_12-45-rootfs.tar.zst"
previous_sha256 = "3896ad34c99f9f7c2b126f7786f451b731df287e1aef7f0058bcb47f20bee63a"

current_version = "latest01"
current_date = "20220316"
old_file = "debian-xfce_amd64_2022-03-02_12-40-rootfs.tar.zst"
old_sha256 = "494489d2d1de23257204959f5473406bdf396b2b9a29d0868df5aa12c9df3382"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-03-16_12-47-rootfs.tar.zst
# SHA256SUM=805da933c7a3620fa2d32079bfd0ffd7a546f991277225d746dacee5039b573f
# BUILD_DATE=20220316
# BUILD_TAG=2022-03-16
# STATUS=completed
# VERSION=latest01
# END_TIME=12:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-16
begin = 2022-03-16 12:22:29.206579369+00:00
start-sync_0 = 12:29:40
start-zstd = 12:33:40
start-sync_1 = 12:46:12
end-sync_1 = 12:47:34
end = 2022-03-16 12:47:34.843525267+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
