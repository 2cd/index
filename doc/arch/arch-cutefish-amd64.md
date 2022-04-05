# arch-cutefish-amd64

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
    --name arch-cutefish-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-cutefish-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-cutefish-amd64 zsh
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

## arch-cutefish-amd64.toml

```toml
[main]
name = "arch"
tag = ["cutefish", "2022-04-05"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "arch-cutefish_amd64_2022-04-05_23-58.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a3c35394322b945bc43967ff47a8d5dbfaacca00d16f176f6f684783a6c68179"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4078907904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1147361042

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220329"
previous_tag = "2022-03-29"
previous_file = "arch-cutefish_amd64_2022-03-29_23-55-rootfs.tar.zst"
previous_sha256 = "0f686448af50182133a114c09f3963804102c0156ccd6f721cd87a3178053a7c"

current_version = "latest02"
current_date = "20220405"
old_file = "arch-cutefish_amd64_2022-03-23_00-48-rootfs.tar.zst"
old_sha256 = "d809c946991fcf84a9aead16c267aa2570eef650efdf03633a8474eccbc9faf0"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-cutefish_amd64_2022-04-05_23-58-rootfs.tar.zst
# SHA256SUM=a3c35394322b945bc43967ff47a8d5dbfaacca00d16f176f6f684783a6c68179
# BUILD_DATE=20220405
# BUILD_TAG=2022-04-05
# STATUS=completed
# VERSION=latest02
# END_TIME=23:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-05
begin = 2022-04-05 23:30:24.778657839+00:00
start-sync_0 = 23:35:42
start-zstd = 23:40:15
start-sync_1 = 23:56:57
end-sync_1 = 23:58:16
end = 2022-04-05 23:58:16.534072486+00:00

[server]
repo = "cake233/arch-cutefish-amd64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
