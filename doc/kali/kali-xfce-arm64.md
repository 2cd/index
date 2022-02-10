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

```sh
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
tag = ["xfce", "2022-02-10"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "kali-xfce_arm64_2022-02-10_13-54.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0ce93946f7ad2dbece815ae456c2178238b1ead3dbd890c0ec1e0e2f5b4df705"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5846575616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1632192418

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220203"
previous_tag = "2022-02-03"
previous_file = "kali-xfce_arm64_2022-02-03_13-44-rootfs.tar.zst"
previous_sha256 = "31400e9be840073631cbcfc76efbc72fa9439fe6e9ff7d02f53d06d4df7524e9"

current_version = "latest02"
current_date = "20220210"
old_file = "kali-xfce_arm64_2022-01-27_14-01-rootfs.tar.zst"
old_sha256 = "b578323eff0dddc90d2ac3461c7f25022981328e0eaae12b280be06c756ffd9d"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-02-10_13-54-rootfs.tar.zst
# SHA256SUM=0ce93946f7ad2dbece815ae456c2178238b1ead3dbd890c0ec1e0e2f5b4df705
# BUILD_DATE=20220210
# BUILD_TAG=2022-02-10
# STATUS=completed
# VERSION=latest02
# END_TIME=13:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-10
begin = 2022-02-10 12:21:21.468135523+00:00
start-sync_0 = 13:27:42
start-zstd = 13:34:36
start-sync_1 = 13:52:19
end-sync_1 = 13:54:07
end = 2022-02-10 13:54:07.893092920+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
zsh = 'zsh 5.8 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
