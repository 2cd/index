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
tag = ["xfce", "2023-11-15"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2023-11-15_12-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "451ef96e57853e1bc231a2d9906e936ecf370e2fae7131f89dff8d51b3097aaa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4298420224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1195187335

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231108"
previous_tag = "2023-11-08"
previous_file = "debian-xfce_amd64_2023-11-08_12-50-rootfs.tar.zst"
previous_sha256 = "09f3f5e1e7ccf30aceaa664d145030c206b7e494430a26582e44eb8f62332986"

current_version = "latest02"
current_date = "20231115"
old_file = "debian-xfce_amd64_2023-10-25_13-20-rootfs.tar.zst"
old_sha256 = "b51568c32d8977218bb42147481699796b7ff60643670db549501358c14c6fb2"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2023-11-15_12-50-rootfs.tar.zst
# SHA256SUM=451ef96e57853e1bc231a2d9906e936ecf370e2fae7131f89dff8d51b3097aaa
# BUILD_DATE=20231115
# BUILD_TAG=2023-11-15
# STATUS=completed
# VERSION=latest02
# END_TIME=12:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-15
begin = 2023-11-15 12:31:44.653371007+00:00
start-sync_0 = 12:36:31
start-zstd = 12:38:52
start-sync_1 = 12:49:59
end-sync_1 = 12:50:52
end = 2023-11-15 12:50:52.270007810+00:00

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
