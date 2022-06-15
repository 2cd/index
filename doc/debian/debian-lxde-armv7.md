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
tag = ["lxde", "2022-06-15"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2022-06-15_13-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2add3ddd7355a4fbda5af0ad52d925010173618cf2257c77e1cd61b7ad36ce45"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.9G"
tar_bytes = 3009719296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "928M"
zstd_bytes = 972810161

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220608"
previous_tag = "2022-06-08"
previous_file = "debian-lxde_armhf_2022-06-08_12-56-rootfs.tar.zst"
previous_sha256 = "9f4f47419e1d7f91e38977ca7e503e6911f8a61e6f1a1982485f7291f32bdbcb"

current_version = "latest01"
current_date = "20220615"
old_file = "debian-lxde_armhf_2022-06-01_12-54-rootfs.tar.zst"
old_sha256 = "7d4d1c1439727fcab6d1e62b7ac17368b49a46f9efc6513b8c1931ae879dac70"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-06-15_13-06-rootfs.tar.zst
# SHA256SUM=2add3ddd7355a4fbda5af0ad52d925010173618cf2257c77e1cd61b7ad36ce45
# BUILD_DATE=20220615
# BUILD_TAG=2022-06-15
# STATUS=completed
# VERSION=latest01
# END_TIME=13:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-15
begin = 2022-06-15 12:19:24.669374360+00:00
start-sync_0 = 12:51:42
start-zstd = 12:54:15
start-sync_1 = 13:05:41
end-sync_1 = 13:06:48
end = 2022-06-15 13:06:48.845593048+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
