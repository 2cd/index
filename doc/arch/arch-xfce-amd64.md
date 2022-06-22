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
tag = ["xfce", "2022-06-22"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_amd64_2022-06-22_00-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "02492dc96b072847fa0634612d60960abd486635972116e6a0a257377d56f6b3"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3808460288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1129934428

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220615"
previous_tag = "2022-06-15"
previous_file = "arch-xfce_amd64_2022-06-15_00-55-rootfs.tar.zst"
previous_sha256 = "90c16c35f7e4032ed7750b8a4eb531f83daaa6351d4b40f4e52ee8694962f7d2"

current_version = "latest01"
current_date = "20220622"
old_file = "arch-xfce_amd64_2022-06-08_00-53-rootfs.tar.zst"
old_sha256 = "4bd0f7f86d3fad66d4f8850cded78ffa455cd0721104b9c4f8012626d137cd79"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2022-06-22_00-53-rootfs.tar.zst
# SHA256SUM=02492dc96b072847fa0634612d60960abd486635972116e6a0a257377d56f6b3
# BUILD_DATE=20220622
# BUILD_TAG=2022-06-22
# STATUS=completed
# VERSION=latest01
# END_TIME=00:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-22
begin = 2022-06-22 00:27:17.753136000+00:00
start-sync_0 = 00:31:41
start-zstd = 00:35:53
start-sync_1 = 00:52:26
end-sync_1 = 00:53:48
end = 2022-06-22 00:53:48.743813850+00:00

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
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
