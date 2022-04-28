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
tag = ["xfce", "2022-04-28"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2022-04-28_13-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "50816cb6b95f89393d078595b8d080eb5ebec423fb00bf2a5a02334cdbee7769"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.4G"
tar_bytes = 5772006400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1614677281

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220421"
previous_tag = "2022-04-21"
previous_file = "kali-xfce_amd64_2022-04-21_13-01-rootfs.tar.zst"
previous_sha256 = "26f0050f9f9778710c1421b4ac5c3eeb21fa5f69a5257544c9929fdee6b6f9e3"

current_version = "latest01"
current_date = "20220428"
old_file = "kali-xfce_amd64_2022-04-14_12-56-rootfs.tar.zst"
old_sha256 = "ad1cfb4c9623f1eb76357fade402b217dde20d169a961747179bb0df527543c8"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2022-04-28_13-03-rootfs.tar.zst
# SHA256SUM=50816cb6b95f89393d078595b8d080eb5ebec423fb00bf2a5a02334cdbee7769
# BUILD_DATE=20220428
# BUILD_TAG=2022-04-28
# STATUS=completed
# VERSION=latest01
# END_TIME=13:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-28
begin = 2022-04-28 12:21:07.308389454+00:00
start-sync_0 = 12:32:52
start-zstd = 12:39:59
start-sync_1 = 13:02:09
end-sync_1 = 13:03:59
end = 2022-04-28 13:03:59.908572549+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
