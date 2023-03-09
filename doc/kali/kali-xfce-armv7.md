# kali-xfce-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name kali-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-armv7 zsh
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

## kali-xfce-armv7.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-03-09"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-03-09_13-46.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f395bef66135b312c584b541e967837a041accad85bcd049cacef472b29618dc"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2843809280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "806M"
zstd_bytes = 844145466

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230302"
previous_tag = "2023-03-02"
previous_file = "kali-xfce_armhf_2023-03-02_13-40-rootfs.tar.zst"
previous_sha256 = "ebac9ee2db23bca63c7491c791e75dc12791b58795aa6b3d1c2b1636d71aa9ac"

current_version = "latest01"
current_date = "20230309"
old_file = "kali-xfce_armhf_2023-02-23_13-27-rootfs.tar.zst"
old_sha256 = "936f34f6bb3784e1973092b7603d208f6b3f3aa043a1b622f35245dfe9d4449d"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-03-09_13-46-rootfs.tar.zst
# SHA256SUM=f395bef66135b312c584b541e967837a041accad85bcd049cacef472b29618dc
# BUILD_DATE=20230309
# BUILD_TAG=2023-03-09
# STATUS=completed
# VERSION=latest01
# END_TIME=13:46

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-09
begin = 2023-03-09 12:24:58.221672813+00:00
start-sync_0 = 13:31:37
start-zstd = 13:34:00
start-sync_1 = 13:45:33
end-sync_1 = 13:46:35
end = 2023-03-09 13:46:35.676451597+00:00

[server]
repo = "cake233/kali-xfce-armv7"

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
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
