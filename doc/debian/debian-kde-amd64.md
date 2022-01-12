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

## debian-kde-amd64.toml

```toml
[main]
name = "debian"
tag = ["kde", "2022-01-12"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "debian-kde_amd64_2022-01-12_12-52.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "950b3599531747374a45aa91282a0df397a64f00c070abf00af9987d67e94236"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5070576128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1523225174

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220105"
previous_tag = "2022-01-05"
previous_file = "debian-kde_amd64_2022-01-05_12-49-rootfs.tar.zst"
previous_sha256 = "3b573d35407974ff53e57b4a559b3a1a0c56434f742ae97eafbaf80abc5a7453"

current_version = "latest02"
current_date = "20220112"
old_file = "debian-kde_amd64_2021-12-22_12-55-rootfs.tar.zst"
old_sha256 = "3661d3b5a4ad0a1e56ce43f1c7c57a5c255d72cda1f785d09648e993ac10b25a"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-kde_amd64_2022-01-12_12-52-rootfs.tar.zst
# SHA256SUM=950b3599531747374a45aa91282a0df397a64f00c070abf00af9987d67e94236
# BUILD_DATE=20220112
# BUILD_TAG=2022-01-12
# STATUS=completed
# VERSION=latest02
# END_TIME=12:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-12
begin = 2022-01-12 12:22:32.337807884+00:00
start-sync_0 = 12:30:07
start-zstd = 12:35:42
start-sync_1 = 12:50:57
end-sync_1 = 12:52:42
end = 2022-01-12 12:52:42.047788195+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-2) 2.33'
zsh = 'zsh 5.8 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
