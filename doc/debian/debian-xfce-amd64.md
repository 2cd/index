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
tag = ["xfce", "2023-10-18"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2023-10-18_13-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c1bf0a7f1941bc0385a6fa1a19611c7706afbbd5ff502719398c21e58dba5b5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4302100480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1205555027

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231004"
previous_tag = "2023-10-04"
previous_file = "debian-xfce_amd64_2023-10-04_13-03-rootfs.tar.zst"
previous_sha256 = "74abaf530e2e921b7317f4094e97ab7afb1d1a51f171aea2b37545cdea64d749"

current_version = "latest01"
current_date = "20231018"
old_file = "debian-xfce_amd64_2023-09-27_13-02-rootfs.tar.zst"
old_sha256 = "3dd3d9c7ec0849889b392530793423b4a27ebf3b07e24b0d5866b4de44105739"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2023-10-18_13-11-rootfs.tar.zst
# SHA256SUM=2c1bf0a7f1941bc0385a6fa1a19611c7706afbbd5ff502719398c21e58dba5b5
# BUILD_DATE=20231018
# BUILD_TAG=2023-10-18
# STATUS=completed
# VERSION=latest01
# END_TIME=13:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-18
begin = 2023-10-18 12:46:14.511679693+00:00
start-sync_0 = 12:52:07
start-zstd = 12:55:31
start-sync_1 = 13:10:09
end-sync_1 = 13:11:44
end = 2023-10-18 13:11:44.763038105+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
