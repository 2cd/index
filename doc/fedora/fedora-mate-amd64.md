# fedora-mate-amd64

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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2024-02-06"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2024-02-06_13-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "52d06396e734ef18cd5c31d133ce3dbaf2808840d072e510fca946db738f5dd2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.2G"
tar_bytes = 5491345408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1681252616

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-mate_amd64_2023-11-21_13-03-rootfs.tar.zst"
previous_sha256 = "9ddef718dd19eac49317c615139a065fcd150318d8295eacbe9e28c4bd76ab1b"

current_version = "latest02"
current_date = "20240206"
old_file = "fedora-mate_amd64_2023-11-14_13-21-rootfs.tar.zst"
old_sha256 = "b54aaa7de993ddc643fa91add1d34d844622ecdeba419ae11e5e5329db3e781a"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2024-02-06_13-09-rootfs.tar.zst
# SHA256SUM=52d06396e734ef18cd5c31d133ce3dbaf2808840d072e510fca946db738f5dd2
# BUILD_DATE=20240206
# BUILD_TAG=2024-02-06
# STATUS=completed
# VERSION=latest02
# END_TIME=13:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-06
begin = 2024-02-06 12:45:24.544964651+00:00
start-sync_0 = 12:50:20
start-zstd = 12:53:17
start-sync_1 = 13:07:49
end-sync_1 = 13:09:05
end = 2024-02-06 13:09:05.530827609+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
ldd = 'ldd (GNU libc) 2.38.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
