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
tag = ["xfce", "2022-03-30"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-xfce_amd64_2022-03-30_11-47.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a47af9c7d9a0ab5ee3a9eb72268c14b8c67e2cb670c935e64606780fb1f6fcf8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3878164992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1094874162

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220323"
previous_tag = "2022-03-23"
previous_file = "debian-xfce_amd64_2022-03-23_12-46-rootfs.tar.zst"
previous_sha256 = "65fd32621f65608a6defd72c36554d18ac68756ed88da14cf8aa1d1025c38691"

current_version = "latest01"
current_date = "20220330"
old_file = "debian-xfce_amd64_2022-03-16_12-47-rootfs.tar.zst"
old_sha256 = "805da933c7a3620fa2d32079bfd0ffd7a546f991277225d746dacee5039b573f"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-03-30_11-47-rootfs.tar.zst
# SHA256SUM=a47af9c7d9a0ab5ee3a9eb72268c14b8c67e2cb670c935e64606780fb1f6fcf8
# BUILD_DATE=20220330
# BUILD_TAG=2022-03-30
# STATUS=completed
# VERSION=latest01
# END_TIME=11:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-30
begin = 2022-03-30 11:19:04.599988969+00:00
start-sync_0 = 11:25:40
start-zstd = 11:29:46
start-sync_1 = 11:46:12
end-sync_1 = 11:47:28
end = 2022-03-30 11:47:28.582478005+00:00

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
