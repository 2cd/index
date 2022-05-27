# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-05-27"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2022-05-27_12-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a9dfeccb07280d98842da28f657e4bbc471ca69557996ab4eabd0b1bc019014a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3992841728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1160752349

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220520"
previous_tag = "2022-05-20"
previous_file = "manjaro-xfce_amd64_2022-05-20_12-47-rootfs.tar.zst"
previous_sha256 = "a7ff739571ff1cc28e1e368a76f0df050e1195a8eb0c8fde27d889ab2103977b"

current_version = "latest02"
current_date = "20220527"
old_file = "manjaro-xfce_amd64_2022-05-13_12-42-rootfs.tar.zst"
old_sha256 = "98bd85c3e071d700b5cbd6bcd891b917e25eca9d1d98a4a59e8161d9041ba5d5"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2022-05-27_12-42-rootfs.tar.zst
# SHA256SUM=a9dfeccb07280d98842da28f657e4bbc471ca69557996ab4eabd0b1bc019014a
# BUILD_DATE=20220527
# BUILD_TAG=2022-05-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-27
begin = 2022-05-27 12:20:54.465629966+00:00
start-sync_0 = 12:24:31
start-zstd = 12:27:23
start-sync_1 = 12:41:30
end-sync_1 = 12:42:40
end = 2022-05-27 12:42:40.117973453+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
