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
tag = ["kde", "2023-06-07"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2023-06-07_01-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "26ad21bcc45b4082a23bd8dfcf5fe19e8766c45a6fb60a95f380d90adf2d95aa"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4911572992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1459772845

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230531"
previous_tag = "2023-05-31"
previous_file = "arch-kde_amd64_2023-05-31_01-01-rootfs.tar.zst"
previous_sha256 = "c4fe29046771eecd219e13fb676b3c437202f79e91657b8a653c78941569cfae"

current_version = "latest01"
current_date = "20230607"
old_file = "arch-kde_amd64_2023-05-24_01-06-rootfs.tar.zst"
old_sha256 = "1af088bbbb081e4556df4f5e4ddb47f191301d7d254a0bf41d89599e9205c137"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2023-06-07_01-04-rootfs.tar.zst
# SHA256SUM=26ad21bcc45b4082a23bd8dfcf5fe19e8766c45a6fb60a95f380d90adf2d95aa
# BUILD_DATE=20230607
# BUILD_TAG=2023-06-07
# STATUS=completed
# VERSION=latest01
# END_TIME=01:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-07
begin = 2023-06-07 00:35:30.272687835+00:00
start-sync_0 = 00:39:37
start-zstd = 00:44:17
start-sync_1 = 01:03:28
end-sync_1 = 01:04:54
end = 2023-06-07 01:04:54.129793773+00:00

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
