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
tag = ["xfce", "2023-09-14"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_armhf_2023-09-14_13-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "09f454d1024482ee7a178ec2d5c80e2b85dfc46acdd68e65f241a7a85dc8c6cb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.7G"
tar_bytes = 2862521344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "822M"
zstd_bytes = 860910128

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230907"
previous_tag = "2023-09-07"
previous_file = "kali-xfce_armhf_2023-09-07_13-31-rootfs.tar.zst"
previous_sha256 = "ce050138b2be03fee08695a2c302fc51d444291d4382d7801005f3d9914405cc"

current_version = "latest02"
current_date = "20230914"
old_file = "kali-xfce_armhf_2023-08-31_13-33-rootfs.tar.zst"
old_sha256 = "3986d64f6f515d0790da10aa28be618b89f45f00e752d6ade2239a51c2b16450"
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2023-09-14_13-37-rootfs.tar.zst
# SHA256SUM=09f454d1024482ee7a178ec2d5c80e2b85dfc46acdd68e65f241a7a85dc8c6cb
# BUILD_DATE=20230914
# BUILD_TAG=2023-09-14
# STATUS=completed
# VERSION=latest02
# END_TIME=13:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-14
begin = 2023-09-14 12:29:05.870341091+00:00
start-sync_0 = 13:25:26
start-zstd = 13:27:15
start-sync_1 = 13:36:46
end-sync_1 = 13:37:56
end = 2023-09-14 13:37:56.283819067+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabi)'

[port]
tcp = [5902, 36080]
```
