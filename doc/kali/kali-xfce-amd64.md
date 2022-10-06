# kali-xfce-amd64

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
    --name kali-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-amd64 zsh
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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-10-06"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2022-10-06_12-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "72e4b084f656f6f0ac7ccb3afc94e55826f04ff264ce5a7e1cc27b6a69fdc58c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.9G"
tar_bytes = 4108977152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1179768371

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220929"
previous_tag = "2022-09-29"
previous_file = "kali-xfce_amd64_2022-09-29_12-52-rootfs.tar.zst"
previous_sha256 = "60a2ba6b7636afd7b70264f7f6716d1bc690336c77e26c6a87b6afae65085387"

current_version = "latest02"
current_date = "20221006"
old_file = "kali-xfce_amd64_2022-09-22_13-04-rootfs.tar.zst"
old_sha256 = "517ace9a4a91bcd9ecc6f0f1d0e948e49a45f1e9483fbce21181c0701197f789"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2022-10-06_12-52-rootfs.tar.zst
# SHA256SUM=72e4b084f656f6f0ac7ccb3afc94e55826f04ff264ce5a7e1cc27b6a69fdc58c
# BUILD_DATE=20221006
# BUILD_TAG=2022-10-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-06
begin = 2022-10-06 12:18:38.045484954+00:00
start-sync_0 = 12:28:12
start-zstd = 12:32:42
start-sync_1 = 12:51:05
end-sync_1 = 12:52:31
end = 2022-10-06 12:52:31.759344424+00:00

[server]
repo = "cake233/kali-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
