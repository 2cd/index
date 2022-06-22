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
tag = ["xfce", "2022-06-22"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2022-06-22_12-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "45106a24650ed6c8b97c4f542710af77c53ff73b739d304b55a17481fefc40f7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3972408320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1130375249

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "debian-xfce_amd64_2022-06-15_12-46-rootfs.tar.zst"
previous_sha256 = "a015d6e4371496705f3b7865eedb76ec664d03d277cebdf794e841ac408aedf5"

current_version = "latest01"
current_date = "20220622"
old_file = "debian-xfce_amd64_2022-06-08_12-43-rootfs.tar.zst"
old_sha256 = "d0269254d73488ce17e2651257a1383015458ae2ea1e8d242c61b59824d441db"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-06-22_12-51-rootfs.tar.zst
# SHA256SUM=45106a24650ed6c8b97c4f542710af77c53ff73b739d304b55a17481fefc40f7
# BUILD_DATE=20220622
# BUILD_TAG=2022-06-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-22
begin = 2022-06-22 12:23:42.804171417+00:00
start-sync_0 = 12:30:39
start-zstd = 12:34:49
start-sync_1 = 12:50:35
end-sync_1 = 12:51:49
end = 2022-06-22 12:51:49.121535468+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
