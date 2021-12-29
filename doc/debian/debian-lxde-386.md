# debian-lxde-386

## How to run it?

```sh
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

```sh
    docker exex -it debian-lxde-386 zsh
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

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2021-12-29"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
x11_or_wayland = true

[file]
name = "debian-lxde_i386_2021-12-29_13-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a3226e5809d0cb764b526776724192d9b1ea70d08052f0d4ee913f4403f16683"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3469274624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "980M"
zstd_bytes = 1027345845

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211222"
previous_tag = "2021-12-22"
previous_file = "debian-lxde_i386_2021-12-22_13-23-rootfs.tar.zst"
previous_sha256 = "d829d951c2c7f06e41d6df5e90078741e868f5820e59caf2daabe90355c76d62"

current_version = "latest01"
current_date = "20211229"
old_file = "debian-lxde_i386_2021-12-15_13-21-rootfs.tar.zst"
old_sha256 = "6ac564c39e7c41ebdead9a31a0814de4e0857e5c2f7d2fa8c4df5cd6cfa0c05f"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2021-12-29_13-13-rootfs.tar.zst
# SHA256SUM=a3226e5809d0cb764b526776724192d9b1ea70d08052f0d4ee913f4403f16683
# BUILD_DATE=20211229
# BUILD_TAG=2021-12-29
# STATUS=completed
# VERSION=latest01
# END_TIME=13:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-29
begin = 2021-12-29 12:23:53.853755289+00:00
start-sync_0 = 13:01:01
start-zstd = 13:03:53
start-sync_1 = 13:12:35
end-sync_1 = 13:13:38
end = 2021-12-29 13:13:38.815041228+00:00

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
