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

## debian-xfce-amd64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-02-09"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-xfce_amd64_2022-02-09_12-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "42ca278ef71370b3a97f1f96d7d9b9caf98c36633b572e15f0ae52e7bed12664"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.4G"
tar_bytes = 3645916672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "984M"
zstd_bytes = 1030772048

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220202"
previous_tag = "2022-02-02"
previous_file = "debian-xfce_amd64_2022-02-02_12-41-rootfs.tar.zst"
previous_sha256 = "8e87ae5ea3dd38211126793c1698c5d5fe10ab88456177adba1913139ac7641c"

current_version = "latest02"
current_date = "20220209"
old_file = "debian-xfce_amd64_2022-01-26_12-43-rootfs.tar.zst"
old_sha256 = "d429f29d9ea13591bd404911cc5096b8bd18701d69782cf569404951483aed27"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-02-09_12-40-rootfs.tar.zst
# SHA256SUM=42ca278ef71370b3a97f1f96d7d9b9caf98c36633b572e15f0ae52e7bed12664
# BUILD_DATE=20220209
# BUILD_TAG=2022-02-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-09
begin = 2022-02-09 12:22:11.517512396+00:00
start-sync_0 = 12:27:47
start-zstd = 12:30:49
start-sync_1 = 12:39:21
end-sync_1 = 12:40:24
end = 2022-02-09 12:40:24.802427050+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-5) 2.33'
zsh = 'zsh 5.8 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
