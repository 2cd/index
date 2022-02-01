# ubuntu-kde-amd64

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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2022-02-01", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-kde_amd64_2022-02-01_00-48.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2611643260b44151b5f6d536f7de0a00eaa66925ba0a142b3b58286c175e6cc6"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3870751744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1090202709

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220125"
previous_tag = "2022-01-25"
previous_file = "ubuntu-kde_amd64_2022-01-25_00-45-rootfs.tar.zst"
previous_sha256 = "2cc65f170bfa172bef979fb9d0724b08db12f74bd387212aba5e5faa65759338"

current_version = "latest02"
current_date = "20220201"
old_file = "ubuntu-kde_amd64_2022-01-18_00-44-rootfs.tar.zst"
old_sha256 = "187664a2e27bd4fcee6c8d77f3a81f239cdc1bc6ef4f6f72efdca668c7af3ea6"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-02-01_00-48-rootfs.tar.zst
# SHA256SUM=2611643260b44151b5f6d536f7de0a00eaa66925ba0a142b3b58286c175e6cc6
# BUILD_DATE=20220201
# BUILD_TAG=2022-02-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-01
begin = 2022-02-01 00:27:22.947551009+00:00
start-sync_0 = 00:33:12
start-zstd = 00:36:30
start-sync_1 = 00:47:45
end-sync_1 = 00:48:53
end = 2022-02-01 00:48:53.269386352+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
