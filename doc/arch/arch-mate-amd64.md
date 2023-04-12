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
tag = ["mate", "2023-04-12"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_amd64_2023-04-12_00-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7f0fd93ab10a5de6a2468678af1b37fa7241480c742f4ba0b7765cf270c92cae"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4797227008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1370441921

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230405"
previous_tag = "2023-04-05"
previous_file = "arch-mate_amd64_2023-04-05_00-56-rootfs.tar.zst"
previous_sha256 = "ef0d99995d7165041fa5d33a17e43ca8d756acac36cf705da73ccd0c6e05010c"

current_version = "latest01"
current_date = "20230412"
old_file = "arch-mate_amd64_2023-03-22_01-14-rootfs.tar.zst"
old_sha256 = "49c857eb96bacf26712c45767ee0a1dc252124e5c8dbc80c1810ef552210f075"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-mate_amd64_2023-04-12_00-55-rootfs.tar.zst
# SHA256SUM=7f0fd93ab10a5de6a2468678af1b37fa7241480c742f4ba0b7765cf270c92cae
# BUILD_DATE=20230412
# BUILD_TAG=2023-04-12
# STATUS=completed
# VERSION=latest01
# END_TIME=00:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-12
begin = 2023-04-12 00:28:52.815561417+00:00
start-sync_0 = 00:33:13
start-zstd = 00:38:00
start-sync_1 = 00:54:40
end-sync_1 = 00:55:58
end = 2023-04-12 00:55:58.085058810+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
