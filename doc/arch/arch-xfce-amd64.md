# arch-xfce-amd64

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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-amd64 zsh
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

## arch-xfce-amd64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-05-11"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_amd64_2022-05-11_01-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9c70f115854a5873d06eee0c34f02b005541c6c68cb4744fccef77ad301f4cae"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3864299520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1130964723

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220504"
previous_tag = "2022-05-04"
previous_file = "arch-xfce_amd64_2022-05-04_00-54-rootfs.tar.zst"
previous_sha256 = "03396d7ac9dde354ba7160e1cba4e41ed657386657fd5601c7a2115ef039527b"

current_version = "latest01"
current_date = "20220511"
old_file = "arch-xfce_amd64_2022-04-27_00-55-rootfs.tar.zst"
old_sha256 = "7dc328b78b63724d2e73ce8ede2d75d13b4bb8ab275d8eb110852226154f0494"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2022-05-11_01-00-rootfs.tar.zst
# SHA256SUM=9c70f115854a5873d06eee0c34f02b005541c6c68cb4744fccef77ad301f4cae
# BUILD_DATE=20220511
# BUILD_TAG=2022-05-11
# STATUS=completed
# VERSION=latest01
# END_TIME=01:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-11
begin = 2022-05-11 00:34:23.053129662+00:00
start-sync_0 = 00:39:21
start-zstd = 00:43:22
start-sync_1 = 00:59:32
end-sync_1 = 01:00:51
end = 2022-05-11 01:00:51.555552166+00:00

[server]
repo = "cake233/arch-xfce-amd64"

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
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
