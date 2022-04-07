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
tag = ["xfce", "2022-04-07"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "kali-xfce_arm64_2022-04-07_18-55.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "17efe710241d89eb312cd80f007ade6cfd10600b22190c94235a39d43196abfd"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.5G"
tar_bytes = 5901500416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1628609489

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220331"
previous_tag = "2022-03-31"
previous_file = "kali-xfce_arm64_2022-03-31_12-36-rootfs.tar.zst"
previous_sha256 = "aca49f9af30774d4483a19bddf876a3057dfd2efffef67907f2e504df5430704"

current_version = "latest01"
current_date = "20220407"
old_file = "kali-xfce_arm64_2022-03-24_13-46-rootfs.tar.zst"
old_sha256 = "89edf17557260a9d9c1569a29683a69ca08ce14f32f70fd60f038aa6f64cd31a"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-04-07_18-55-rootfs.tar.zst
# SHA256SUM=17efe710241d89eb312cd80f007ade6cfd10600b22190c94235a39d43196abfd
# BUILD_DATE=20220407
# BUILD_TAG=2022-04-07
# STATUS=completed
# VERSION=latest01
# END_TIME=18:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-07
begin = 2022-04-07 17:23:19.133904016+00:00
start-sync_0 = 18:23:59
start-zstd = 18:31:02
start-sync_1 = 18:53:43
end-sync_1 = 18:55:39
end = 2022-04-07 18:55:39.926550906+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
