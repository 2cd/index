# debian-kde-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name debian-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-arm64 zsh
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

## debian-kde-arm64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2023-10-04"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_arm64_2023-10-04_14-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "edcb5adf9504d793842cb11cd34f38397f4309084f24760455fd7c33b8eca07a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.2G"
tar_bytes = 6579494912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1829267444

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230927"
previous_tag = "2023-09-27"
previous_file = "debian-kde_arm64_2023-09-27_14-44-rootfs.tar.zst"
previous_sha256 = "fecfab4907cde67126bf4693578b0531b76a4d8df16badcd7936719e945f7fb3"

current_version = "latest02"
current_date = "20231004"
old_file = "debian-kde_arm64_2023-09-20_14-47-rootfs.tar.zst"
old_sha256 = "1807e1857b68e2ca067a1a9407492feae7bd3333e2b9aee493aeb9baafef485c"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-kde_arm64_2023-10-04_14-53-rootfs.tar.zst
# SHA256SUM=edcb5adf9504d793842cb11cd34f38397f4309084f24760455fd7c33b8eca07a
# BUILD_DATE=20231004
# BUILD_TAG=2023-10-04
# STATUS=completed
# VERSION=latest02
# END_TIME=14:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-04
begin = 2023-10-04 12:37:42.308221841+00:00
start-sync_0 = 14:23:01
start-zstd = 14:28:42
start-sync_1 = 14:51:13
end-sync_1 = 14:53:50
end = 2023-10-04 14:53:50.509430382+00:00

[server]
repo = "cake233/debian-kde-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
