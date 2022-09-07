# arch-kde-amd64

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
    --name arch-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-amd64 zsh
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

## arch-kde-amd64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-09-07"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2022-09-07_00-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6f363100dc55dd4230124dc09a96917ec54b6f3c62151690aca5766372e4baea"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4740358656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1368714774

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220831"
previous_tag = "2022-08-31"
previous_file = "arch-kde_amd64_2022-08-31_01-20-rootfs.tar.zst"
previous_sha256 = "e9fbdef82845bfcaacc6677ef0944479e5eaec624d4c77306fa7b5957dd52fdd"

current_version = "latest01"
current_date = "20220907"
old_file = "arch-kde_amd64_2022-08-24_01-15-rootfs.tar.zst"
old_sha256 = "6bc8d1f726285b4b5f4420fca6940d5b6800b49a217a0dc15ef9e600665d76b0"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2022-09-07_00-55-rootfs.tar.zst
# SHA256SUM=6f363100dc55dd4230124dc09a96917ec54b6f3c62151690aca5766372e4baea
# BUILD_DATE=20220907
# BUILD_TAG=2022-09-07
# STATUS=completed
# VERSION=latest01
# END_TIME=00:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-07
begin = 2022-09-07 00:29:07.035496008+00:00
start-sync_0 = 00:33:15
start-zstd = 00:37:55
start-sync_1 = 00:53:48
end-sync_1 = 00:55:01
end = 2022-09-07 00:55:01.930535852+00:00

[server]
repo = "cake233/arch-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
