# debian-kde-amd64

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
    --name debian-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-kde-amd64 zsh
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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-12-21"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-kde_amd64_2022-12-21_12-38.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8098821a861484d3ae18350bf35230160887cfa126a3b30684f386972f44a633"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3443671040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "906M"
zstd_bytes = 949173747

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221214"
previous_tag = "2022-12-14"
previous_file = "debian-kde_amd64_2022-12-14_13-02-rootfs.tar.zst"
previous_sha256 = "e8658d0c877b887dabb796b18161d34ded686ca1495439c22d59b5949f1f08f8"

current_version = "latest02"
current_date = "20221221"
old_file = "debian-kde_amd64_2022-12-07_12-51-rootfs.tar.zst"
old_sha256 = "7de1934100570bb9fe429c8ae0fe2bca67fccc16f80757b5be779dca32560add"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-12-21_12-38-rootfs.tar.zst
# SHA256SUM=8098821a861484d3ae18350bf35230160887cfa126a3b30684f386972f44a633
# BUILD_DATE=20221221
# BUILD_TAG=2022-12-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:38

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-21
begin = 2022-12-21 12:19:38.943720587+00:00
start-sync_0 = 12:24:03
start-zstd = 12:26:41
start-sync_1 = 12:37:49
end-sync_1 = 12:38:42
end = 2022-12-21 12:38:42.705418326+00:00

[server]
repo = "cake233/debian-kde-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
