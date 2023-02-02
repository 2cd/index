# kali-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-02-02"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2023-02-02_13-31.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "17c43593a0a17062ea214c686dc2528b5c19cfba39036b7f710b4397900aad0c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5292035584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1464207350

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230126"
previous_tag = "2023-01-26"
previous_file = "kali-xfce_arm64_2023-01-26_13-42-rootfs.tar.zst"
previous_sha256 = "5399c0ba829b1923ef869cccfee7386ca4dfc071c0698ef4179058febdf1e59d"

current_version = "latest02"
current_date = "20230202"
old_file = "kali-xfce_arm64_2023-01-19_13-41-rootfs.tar.zst"
old_sha256 = "5ff5440097326cfcb762e9423ae52aa7a1c1c6cb119a5fc9a39ad642c1e912b6"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2023-02-02_13-31-rootfs.tar.zst
# SHA256SUM=17c43593a0a17062ea214c686dc2528b5c19cfba39036b7f710b4397900aad0c
# BUILD_DATE=20230202
# BUILD_TAG=2023-02-02
# STATUS=completed
# VERSION=latest02
# END_TIME=13:31

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-02
begin = 2023-02-02 12:28:19.603250342+00:00
start-sync_0 = 13:09:08
start-zstd = 13:13:21
start-sync_1 = 13:30:22
end-sync_1 = 13:31:50
end = 2023-02-02 13:31:50.428158938+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
