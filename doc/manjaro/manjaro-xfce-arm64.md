# manjaro-xfce-arm64

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
    --name manjaro-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-arm64 zsh
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

## manjaro-xfce-arm64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-03-03"]
os = "manjaro"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_arm64_2023-03-03_12-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b86d489d64293d1e628c205c5b8a68b244621e1af9f4942bd5e3b46ebd121bd8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4523202560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1309590922

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230224"
previous_tag = "2023-02-24"
previous_file = "manjaro-xfce_arm64_2023-02-24_12-53-rootfs.tar.zst"
previous_sha256 = "e30aeb2dbc495efedf2c6aa193caa546324156e9dacdb9952225f174c475c7ee"

current_version = "latest01"
current_date = "20230303"
old_file = "manjaro-xfce_arm64_2023-02-17_13-03-rootfs.tar.zst"
old_sha256 = "a7b95400aaa687be3e3d99f670457720d95a045824f54097fdb426d9054b5415"
# edition 2021
# DISTRO_NAME=manjaro-stable_arm64
# ROOTFS_FILE=manjaro-xfce_arm64_2023-03-03_12-54-rootfs.tar.zst
# SHA256SUM=b86d489d64293d1e628c205c5b8a68b244621e1af9f4942bd5e3b46ebd121bd8
# BUILD_DATE=20230303
# BUILD_TAG=2023-03-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-03
begin = 2023-03-03 12:20:44.483109959+00:00
start-sync_0 = 12:34:23
start-zstd = 12:37:58
start-sync_1 = 12:53:24
end-sync_1 = 12:54:44
end = 2023-03-03 12:54:44.104753448+00:00

[server]
repo = "cake233/manjaro-xfce-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
