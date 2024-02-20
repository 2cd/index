# ubuntu-mate-amd64

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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2024-02-20", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2024-02-20_01-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0a5a8d6cf77f2b4a4874a162ff531e27585d6a6d91ad50671a7999cb175a5e5b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3912398848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "990M"
zstd_bytes = 1037559962

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-mate_amd64_2023-11-28_00-45-rootfs.tar.zst"
previous_sha256 = "9c9d6fe41799b22ebcb7544926072ddb9e3a6dc2c44b555ebe598f4900527fc3"

current_version = "latest02"
current_date = "20240220"
old_file = "ubuntu-mate_amd64_2023-11-21_00-43-rootfs.tar.zst"
old_sha256 = "4d460a3a1770d73aac7d97068cab930745f5cfa0631b33846c0efb7ed96549c6"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2024-02-20_01-00-rootfs.tar.zst
# SHA256SUM=0a5a8d6cf77f2b4a4874a162ff531e27585d6a6d91ad50671a7999cb175a5e5b
# BUILD_DATE=20240220
# BUILD_TAG=2024-02-20
# STATUS=completed
# VERSION=latest02
# END_TIME=01:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-20
begin = 2024-02-20 00:43:00.282836682+00:00
start-sync_0 = 00:47:46
start-zstd = 00:49:57
start-sync_1 = 00:59:38
end-sync_1 = 01:00:24
end = 2024-02-20 01:00:24.904361651+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
