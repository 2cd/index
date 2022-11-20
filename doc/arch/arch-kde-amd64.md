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
tag = ["kde", "2022-11-20"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2022-11-20_18-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6665a52c8e21c91e51ce85aaf93410f79c221f774faa62e1f7bda2c0f7ac2b29"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4816967680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1406266297

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221116"
previous_tag = "2022-11-16"
previous_file = "arch-kde_amd64_2022-11-16_00-40-rootfs.tar.zst"
previous_sha256 = "a53a11484af87642231e21a8307b01581349fc6d5d23526ce9ea9d1d198bd84e"

current_version = "latest02"
current_date = "20221120"
old_file = "arch-kde_amd64_2022-11-09_01-51-rootfs.tar.zst"
old_sha256 = "a83af6d4cdd63de44b59711f7c396cb80ccdbf3d9b36399cca5fc81f7f53146c"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2022-11-20_18-54-rootfs.tar.zst
# SHA256SUM=6665a52c8e21c91e51ce85aaf93410f79c221f774faa62e1f7bda2c0f7ac2b29
# BUILD_DATE=20221120
# BUILD_TAG=2022-11-20
# STATUS=completed
# VERSION=latest02
# END_TIME=18:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-20
begin = 2022-11-20 18:25:22.347289202+00:00
start-sync_0 = 18:30:28
start-zstd = 18:35:58
start-sync_1 = 18:52:52
end-sync_1 = 18:54:38
end = 2022-11-20 18:54:38.618506926+00:00

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
