# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2022-11-15", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2022-11-15_00-36.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "07d6d2eaa08465ea272bd9cf49c89cac6252a5f26c52e496152147bc8709a7c9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3997208064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1080586314

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221108"
previous_tag = "2022-11-08"
previous_file = "ubuntu-lxqt_amd64_2022-11-08_00-29-rootfs.tar.zst"
previous_sha256 = "ba7dfb25cd365153d4a04e51d7e8c58d8ffd6cf8b2a8918d4447c0dd057a0a9d"

current_version = "latest02"
current_date = "20221115"
old_file = "ubuntu-lxqt_amd64_2022-11-01_00-35-rootfs.tar.zst"
old_sha256 = "bb5c4544026ec400b48273608b2b4533d7a3bab00f72ee4634148d4a5a7fd9f4"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-11-15_00-36-rootfs.tar.zst
# SHA256SUM=07d6d2eaa08465ea272bd9cf49c89cac6252a5f26c52e496152147bc8709a7c9
# BUILD_DATE=20221115
# BUILD_TAG=2022-11-15
# STATUS=completed
# VERSION=latest02
# END_TIME=00:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-15
begin = 2022-11-15 00:03:11.435039974+00:00
start-sync_0 = 00:12:09
start-zstd = 00:16:25
start-sync_1 = 00:35:05
end-sync_1 = 00:36:23
end = 2022-11-15 00:36:23.129485919+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
