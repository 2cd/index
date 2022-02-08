# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-02-08", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_amd64_2022-02-08_00-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5042820a4fcda853f746d99dbc5dcf30537fcfc375d7f288dfcf86d0999e3c37"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2980168192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "763M"
zstd_bytes = 800017036

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220201"
previous_tag = "2022-02-01"
previous_file = "ubuntu-xfce_amd64_2022-02-01_00-43-rootfs.tar.zst"
previous_sha256 = "e7a846a45dfe2c75a9105069ae89380e603d8048f30381820e378d0e0f00feee"

current_version = "latest01"
current_date = "20220208"
old_file = "ubuntu-xfce_amd64_2022-01-25_00-37-rootfs.tar.zst"
old_sha256 = "d2205e986642bfc967bd710483435e1fa7b5117a2e5dd66d7c7aa5bffc38e359"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-02-08_00-40-rootfs.tar.zst
# SHA256SUM=5042820a4fcda853f746d99dbc5dcf30537fcfc375d7f288dfcf86d0999e3c37
# BUILD_DATE=20220208
# BUILD_TAG=2022-02-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-08
begin = 2022-02-08 00:22:51.967567294+00:00
start-sync_0 = 00:28:42
start-zstd = 00:31:26
start-sync_1 = 00:40:03
end-sync_1 = 00:40:59
end = 2022-02-08 00:40:59.566028627+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
