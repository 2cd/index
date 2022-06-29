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
tag = ["mate", "2022-06-29"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_amd64_2022-06-29_01-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e1ac0f8d19531f9f65562f20dd8c99b73ded783813c417dad3044dd97a87a6ec"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4726195200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1336190590

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220622"
previous_tag = "2022-06-22"
previous_file = "arch-mate_amd64_2022-06-22_00-58-rootfs.tar.zst"
previous_sha256 = "1f2a449c819b9bcd3f8bde438a793863aa7b9c7a4cdd1079c594446c10928a5f"

current_version = "latest02"
current_date = "20220629"
old_file = "arch-mate_amd64_2022-06-15_00-58-rootfs.tar.zst"
old_sha256 = "30d4331bf2176e7508df9e150db544c33239f1e0b20f69a738095b32c283795f"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2022-06-29_01-03-rootfs.tar.zst
# SHA256SUM=e1ac0f8d19531f9f65562f20dd8c99b73ded783813c417dad3044dd97a87a6ec
# BUILD_DATE=20220629
# BUILD_TAG=2022-06-29
# STATUS=completed
# VERSION=latest02
# END_TIME=01:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-29
begin = 2022-06-29 00:32:04.982345430+00:00
start-sync_0 = 00:37:17
start-zstd = 00:43:00
start-sync_1 = 01:01:56
end-sync_1 = 01:03:34
end = 2022-06-29 01:03:34.323083391+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
