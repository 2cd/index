# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-11-28"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-11-28_13-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ba470d0fc2965427d1bde9db53bffefbc80b3cae53a2b5eeb9640757ddeb05f0"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.6G"
tar_bytes = 5939113472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1892737155

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231121"
previous_tag = "2023-11-21"
previous_file = "fedora-kde_amd64_2023-11-21_13-04-rootfs.tar.zst"
previous_sha256 = "c6a87a864db035419ee5f0defa12060f813b3f7030d2d095e77c8ba4ebbd84c2"

current_version = "latest02"
current_date = "20231128"
old_file = "fedora-kde_amd64_2023-11-14_13-26-rootfs.tar.zst"
old_sha256 = "b42cf55a6eb4bac0acc3e59f3622d671171b57764aae015f9f34ab9403ba381b"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-11-28_13-07-rootfs.tar.zst
# SHA256SUM=ba470d0fc2965427d1bde9db53bffefbc80b3cae53a2b5eeb9640757ddeb05f0
# BUILD_DATE=20231128
# BUILD_TAG=2023-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=13:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-28
begin = 2023-11-28 12:40:18.941419711+00:00
start-sync_0 = 12:46:05
start-zstd = 12:49:17
start-sync_1 = 13:06:18
end-sync_1 = 13:07:38
end = 2023-11-28 13:07:38.570013075+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
