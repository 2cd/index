# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-04-15"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "manjaro-xfce_amd64_2022-04-15_12-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "94366acab2a53f896eeac61b5307db4f591e5dcfd741d97248b4d6ed3538eb6a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3854963712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1129067614

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220408"
previous_tag = "2022-04-08"
previous_file = "manjaro-xfce_amd64_2022-04-08_11-42-rootfs.tar.zst"
previous_sha256 = "2913ade616026034e56d51af857fa832be50a3e20ee3bf90431a9821feda2f8e"

current_version = "latest02"
current_date = "20220415"
old_file = "manjaro-xfce_amd64_2022-04-01_11-43-rootfs.tar.zst"
old_sha256 = "87ca7e620c72233561d51766627ec5b3017628c190e8e17bfa6ac6f483db5f7e"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2022-04-15_12-41-rootfs.tar.zst
# SHA256SUM=94366acab2a53f896eeac61b5307db4f591e5dcfd741d97248b4d6ed3538eb6a
# BUILD_DATE=20220415
# BUILD_TAG=2022-04-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-15
begin = 2022-04-15 12:19:05.626433840+00:00
start-sync_0 = 12:23:37
start-zstd = 12:26:30
start-sync_1 = 12:40:47
end-sync_1 = 12:41:58
end = 2022-04-15 12:41:58.539751532+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
