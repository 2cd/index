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
tag = ["xfce", "2022-11-25"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2022-11-25_12-36.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e7019b85ad6c03c83276ada1e18c9f7d23d35071949754f8d20d2e662951688e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3921291776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1176394762

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221118"
previous_tag = "2022-11-18"
previous_file = "manjaro-xfce_amd64_2022-11-18_12-27-rootfs.tar.zst"
previous_sha256 = "57322e8198b6607778524789d4e270df797f5f60d6858d6f80bd868d58308e9a"

current_version = "latest01"
current_date = "20221125"
old_file = "manjaro-xfce_amd64_2022-11-11_12-30-rootfs.tar.zst"
old_sha256 = "c02ae02ef99f468f13e622f6fa51eeababe49a23415870aa6535d13644e0fe41"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2022-11-25_12-36-rootfs.tar.zst
# SHA256SUM=e7019b85ad6c03c83276ada1e18c9f7d23d35071949754f8d20d2e662951688e
# BUILD_DATE=20221125
# BUILD_TAG=2022-11-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:36

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-25
begin = 2022-11-25 12:12:19.706263392+00:00
start-sync_0 = 12:16:13
start-zstd = 12:19:29
start-sync_1 = 12:35:32
end-sync_1 = 12:36:47
end = 2022-11-25 12:36:47.616942700+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
