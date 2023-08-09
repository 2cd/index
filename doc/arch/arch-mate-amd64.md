# arch-mate-amd64

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
    --name arch-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-amd64 zsh
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

## arch-mate-amd64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2023-08-09"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_amd64_2023-08-09_01-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bfaadce397bdcd7e5bf614facdd80e63b06b19b93f5e7e5f6e5acf82f00f6150"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4836784128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1377269178

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230802"
previous_tag = "2023-08-02"
previous_file = "arch-mate_amd64_2023-08-02_01-13-rootfs.tar.zst"
previous_sha256 = "36fb006c35b53a5ec33b8d09d5f6be38d29d87b2e72ce3b1bada7a73a164fa3a"

current_version = "latest02"
current_date = "20230809"
old_file = "arch-mate_amd64_2023-07-26_01-05-rootfs.tar.zst"
old_sha256 = "2387c287c3482f627b1de5a9e10ea7b497a8eb7a08bffbe914134aefd21844d6"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2023-08-09_01-16-rootfs.tar.zst
# SHA256SUM=bfaadce397bdcd7e5bf614facdd80e63b06b19b93f5e7e5f6e5acf82f00f6150
# BUILD_DATE=20230809
# BUILD_TAG=2023-08-09
# STATUS=completed
# VERSION=latest02
# END_TIME=01:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-09
begin = 2023-08-09 00:44:13.274874551+00:00
start-sync_0 = 00:49:46
start-zstd = 00:55:22
start-sync_1 = 01:14:21
end-sync_1 = 01:16:00
end = 2023-08-09 01:16:00.045270860+00:00

[server]
repo = "cake233/arch-mate-amd64"

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
