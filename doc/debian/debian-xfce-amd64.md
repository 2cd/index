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
tag = ["xfce", "2022-09-28"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2022-09-28_12-44.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "636f97fdf6a8884613c67b49f1b7694a4f54c195da3f2ac1c82caceb8d1b395a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3982445056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1132224584

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220921"
previous_tag = "2022-09-21"
previous_file = "debian-xfce_amd64_2022-09-21_12-40-rootfs.tar.zst"
previous_sha256 = "5d362e242450a3a322b3838e6703645689e4b801d60e2b8877cb24763d9adc51"

current_version = "latest02"
current_date = "20220928"
old_file = "debian-xfce_amd64_2022-09-14_12-43-rootfs.tar.zst"
old_sha256 = "b8f916ec48048f45b54620ad1206d6a10f1fc2cc050d34043ad27c7f4010b14f"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-09-28_12-44-rootfs.tar.zst
# SHA256SUM=636f97fdf6a8884613c67b49f1b7694a4f54c195da3f2ac1c82caceb8d1b395a
# BUILD_DATE=20220928
# BUILD_TAG=2022-09-28
# STATUS=completed
# VERSION=latest02
# END_TIME=12:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-28
begin = 2022-09-28 12:21:08.564264900+00:00
start-sync_0 = 12:26:49
start-zstd = 12:30:03
start-sync_1 = 12:43:24
end-sync_1 = 12:44:26
end = 2022-09-28 12:44:26.341339403+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-1) 2.35'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
