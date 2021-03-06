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

## debian-lxde-386.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2022-07-20"]
os = "debian"
release = "sid"
arch = "i386"
platform = "linux/386"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_i386_2022-07-20_13-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "68bec513b51adb7d103672464ebbd57159e69c10b6efdbd304ccfccf7326a0ee"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4175374336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1191497026

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-lxde_i386_2022-07-13_13-10-rootfs.tar.zst"
previous_sha256 = "41d36dc30bfddfa5609d4004cb242e2fa0d2bdd6cfeef8bff2ea0296d7f84f2c"

current_version = "latest01"
current_date = "20220720"
old_file = "debian-lxde_i386_2022-07-06_13-10-rootfs.tar.zst"
old_sha256 = "b18a79c8108e81e1e3e2a3a24a54671a9a108398b749dfd6df1ba9829b04cb51"
# edition 2021
# DISTRO_NAME=debian-sid_i386
# ROOTFS_FILE=debian-lxde_i386_2022-07-20_13-14-rootfs.tar.zst
# SHA256SUM=68bec513b51adb7d103672464ebbd57159e69c10b6efdbd304ccfccf7326a0ee
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=13:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 12:22:52.398000024+00:00
start-sync_0 = 12:55:11
start-zstd = 12:59:36
start-sync_1 = 13:13:27
end-sync_1 = 13:14:44
end = 2022-07-20 13:14:44.613442335+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (i686-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
