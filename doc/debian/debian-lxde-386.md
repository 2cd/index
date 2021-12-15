# debian-lxde-386

## How to run it?

```shell
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not 386, then install qemu & binfmt-support.
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
    --name debian-lxde-386 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-386

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```shell
    docker exex -it debian-lxde-386 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2021-12-15"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = true

[file]
name = "debian-lxde_i386_2021-12-15_13-21.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "6ac564c39e7c41ebdead9a31a0814de4e0857e5c2f7d2fa8c4df5cd6cfa0c05f"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3466738688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "979M"
zstd_bytes = 1026258717

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211208"
previous_tag = "2021-12-08"
previous_file = "debian-lxde_i386_2021-12-08_13-10-rootfs.tar.zst"
previous_sha256 = "8ad783a7787c94b8bfc5756ec4f4903b050ed202e2947fec7df35d93b63c566f"

current_version = "latest01"
current_date = "20211215"
old_file = "debian-lxde_i386_2021-12-01_13-02-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2021-12-15_13-21-rootfs.tar.zst
# SHA256SUM=6ac564c39e7c41ebdead9a31a0814de4e0857e5c2f7d2fa8c4df5cd6cfa0c05f
# BUILD_DATE=20211215
# BUILD_TAG=2021-12-15
# STATUS=completed
# VERSION=latest01
# END_TIME=13:21

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-15
begin = 2021-12-15 12:18:23.445327084+00:00
start-sync_0 = 13:02:46
start-zstd = 13:06:29
start-sync_1 = 13:20:35
end-sync_1 = 13:21:46
end = 2021-12-15 13:21:46.441659386+00:00

[server]
repo = "cake233/debian-lxde-386"

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
