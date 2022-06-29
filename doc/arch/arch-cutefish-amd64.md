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
tag = ["cutefish", "2022-06-29"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_amd64_2022-06-29_01-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "522b645cccbf6d5b5448cbbeb70203f1a533ae151ff5160cb9ffe2f298d346d4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4157647872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1185657537

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220622"
previous_tag = "2022-06-22"
previous_file = "arch-cutefish_amd64_2022-06-22_00-50-rootfs.tar.zst"
previous_sha256 = "4761be1b5a3cf81d287028908261f72d0e498d71737bab51ba84edd2b0810c32"

current_version = "latest02"
current_date = "20220629"
old_file = "arch-cutefish_amd64_2022-06-15_00-56-rootfs.tar.zst"
old_sha256 = "3db00787e7d0b38965a3758307bb1f663fdf0e642c5479b73afa5db1aef62643"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-cutefish_amd64_2022-06-29_01-00-rootfs.tar.zst
# SHA256SUM=522b645cccbf6d5b5448cbbeb70203f1a533ae151ff5160cb9ffe2f298d346d4
# BUILD_DATE=20220629
# BUILD_TAG=2022-06-29
# STATUS=completed
# VERSION=latest02
# END_TIME=01:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-29
begin = 2022-06-29 00:32:01.971727409+00:00
start-sync_0 = 00:37:23
start-zstd = 00:41:48
start-sync_1 = 00:58:43
end-sync_1 = 01:00:01
end = 2022-06-29 01:00:01.144539876+00:00

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
