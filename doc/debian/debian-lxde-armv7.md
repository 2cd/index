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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2022-02-02"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "debian-lxde_armhf_2022-02-02_13-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "61a4f795112b7a6fb768824d217aed50c702cc032e7a2ce5eb35ba3054851414"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2753895424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "874M"
zstd_bytes = 915420336

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220126"
previous_tag = "2022-01-26"
previous_file = "debian-lxde_armhf_2022-01-26_13-01-rootfs.tar.zst"
previous_sha256 = "406b78a8862113fbca89aab65afcf30d705d5643a3f37557dd089f7495325888"

current_version = "latest01"
current_date = "20220202"
old_file = "debian-lxde_armhf_2022-01-19_13-01-rootfs.tar.zst"
old_sha256 = "b9fd5c6f0376dbdd67ff8138123ef60c44d5fccc7d0edcc0b17d39bae587eb8c"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-02-02_13-00-rootfs.tar.zst
# SHA256SUM=61a4f795112b7a6fb768824d217aed50c702cc032e7a2ce5eb35ba3054851414
# BUILD_DATE=20220202
# BUILD_TAG=2022-02-02
# STATUS=completed
# VERSION=latest01
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-02
begin = 2022-02-02 12:21:40.045728309+00:00
start-sync_0 = 12:50:26
start-zstd = 12:52:25
start-sync_1 = 12:59:08
end-sync_1 = 13:00:07
end = 2022-02-02 13:00:07.287604106+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-5) 2.33'
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
