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
tag = ["cutefish", "2022-03-23"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "arch-cutefish_amd64_2022-03-23_00-48.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d809c946991fcf84a9aead16c267aa2570eef650efdf03633a8474eccbc9faf0"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4083488256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1263937201

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "arch-cutefish_amd64_2022-03-16_00-46-rootfs.tar.zst"
previous_sha256 = "555dcb83044dda66fbc56a8a90c4dc16e52046e758c7cbb1476a1b664ef458d1"

current_version = "latest02"
current_date = "20220323"
old_file = "arch-cutefish_amd64_2022-03-09_00-56-rootfs.tar.zst"
old_sha256 = "893f83b56996ae5f5980044fb262c91e85344bb7babdb79bc37b1bc6d23e304a"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-cutefish_amd64_2022-03-23_00-48-rootfs.tar.zst
# SHA256SUM=d809c946991fcf84a9aead16c267aa2570eef650efdf03633a8474eccbc9faf0
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 00:33:25.686966517+00:00
start-sync_0 = 00:38:10
start-zstd = 00:41:57
start-sync_1 = 00:47:44
end-sync_1 = 00:48:59
end = 2022-03-23 00:48:59.928565521+00:00

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
