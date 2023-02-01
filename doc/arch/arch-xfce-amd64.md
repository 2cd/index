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
tag = ["xfce", "2023-02-01"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_amd64_2023-02-01_00-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6f27298c31e765e23154b36265872e851e9695562e805b51f6ef3af2c772d721"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3929768448

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1154020694

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230125"
previous_tag = "2023-01-25"
previous_file = "arch-xfce_amd64_2023-01-25_00-54-rootfs.tar.zst"
previous_sha256 = "c362c2960cd1943b2b14bc30f793e407d7f29375e210df2cc8fc59a84073492e"

current_version = "latest02"
current_date = "20230201"
old_file = "arch-xfce_amd64_2023-01-11_00-49-rootfs.tar.zst"
old_sha256 = "12de434624329a3bfa5d7594f17b6a291207ae624bd309ed42484254808588c6"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2023-02-01_00-54-rootfs.tar.zst
# SHA256SUM=6f27298c31e765e23154b36265872e851e9695562e805b51f6ef3af2c772d721
# BUILD_DATE=20230201
# BUILD_TAG=2023-02-01
# STATUS=completed
# VERSION=latest02
# END_TIME=00:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-01
begin = 2023-02-01 00:31:17.424010607+00:00
start-sync_0 = 00:35:42
start-zstd = 00:39:05
start-sync_1 = 00:53:29
end-sync_1 = 00:54:38
end = 2023-02-01 00:54:38.806010044+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
