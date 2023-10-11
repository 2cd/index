# debian-lxde-armv7

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
    --name debian-lxde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2023-10-11"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2023-10-11_13-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0d55782550d4bdf757146c7264197f489f399191e926fbe892599282441035ad"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3165277696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "953M"
zstd_bytes = 998299761

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231004"
previous_tag = "2023-10-04"
previous_file = "debian-lxde_armhf_2023-10-04_13-14-rootfs.tar.zst"
previous_sha256 = "a003ced86ea41fa6c54fa63657f39aac740bed408f2341d319864a271b17010a"

current_version = "latest01"
current_date = "20231011"
old_file = "debian-lxde_armhf_2023-09-27_13-26-rootfs.tar.zst"
old_sha256 = "f23c453614d27c0a80936314ddc732472340cf57709be4ff1860013e6919c9c1"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2023-10-11_13-28-rootfs.tar.zst
# SHA256SUM=0d55782550d4bdf757146c7264197f489f399191e926fbe892599282441035ad
# BUILD_DATE=20231011
# BUILD_TAG=2023-10-11
# STATUS=completed
# VERSION=latest01
# END_TIME=13:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-11
begin = 2023-10-11 12:39:41.959691138+00:00
start-sync_0 = 13:12:05
start-zstd = 13:14:36
start-sync_1 = 13:27:20
end-sync_1 = 13:28:42
end = 2023-10-11 13:28:42.338231118+00:00

[server]
repo = "cake233/debian-lxde-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
