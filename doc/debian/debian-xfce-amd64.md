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
tag = ["xfce", "2022-08-10"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2022-08-10_12-47.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8d69f63ea5c9678c38bac8aeae871ed84197238e211e934a7a486d9cb016244e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4482606080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1293552314

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-xfce_amd64_2022-07-13_12-45-rootfs.tar.zst"
previous_sha256 = "b7a770eb6cb541446a3b078f3f4efbd09f89cb28e504db2a30aa1abb5837c88f"

current_version = "latest01"
current_date = "20220810"
old_file = "debian-xfce_amd64_2022-07-06_12-53-rootfs.tar.zst"
old_sha256 = "8695135c0d0a0e158cad55955b719ba5bf9b293243bc0ad060acea49beac451f"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-08-10_12-47-rootfs.tar.zst
# SHA256SUM=8d69f63ea5c9678c38bac8aeae871ed84197238e211e934a7a486d9cb016244e
# BUILD_DATE=20220810
# BUILD_TAG=2022-08-10
# STATUS=completed
# VERSION=latest01
# END_TIME=12:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-10
begin = 2022-08-10 12:20:42.393372846+00:00
start-sync_0 = 12:26:56
start-zstd = 12:30:39
start-sync_1 = 12:46:15
end-sync_1 = 12:47:36
end = 2022-08-10 12:47:36.386089945+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-3) 2.34'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
