# fedora-xfce-amd64

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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2022-04-26"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2022-04-26_13-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bfd447d7a7c2e1ac02c811ef45fe7b06b657dc7d7c34c1642ce43d0cff6a1eda"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4059249664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1347138653

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220419"
previous_tag = "2022-04-19"
previous_file = "fedora-xfce_amd64_2022-04-19_13-11-rootfs.tar.zst"
previous_sha256 = "3a0f2420ca0767f5525b0190b4a304fdb706258aa804daf8a5b6a47c79aef394"

current_version = "latest01"
current_date = "20220426"
old_file = "fedora-xfce_amd64_2022-04-12_14-39-rootfs.tar.zst"
old_sha256 = "363567cb294acb9df536a22d3bd0a030f4d5f133dcbb779934ae7150e58eb3f0"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2022-04-26_13-06-rootfs.tar.zst
# SHA256SUM=bfd447d7a7c2e1ac02c811ef45fe7b06b657dc7d7c34c1642ce43d0cff6a1eda
# BUILD_DATE=20220426
# BUILD_TAG=2022-04-26
# STATUS=completed
# VERSION=latest01
# END_TIME=13:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-26
begin = 2022-04-26 12:38:21.015051773+00:00
start-sync_0 = 12:45:00
start-zstd = 12:49:03
start-sync_1 = 13:05:04
end-sync_1 = 13:06:34
end = 2022-04-26 13:06:34.959050309+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
