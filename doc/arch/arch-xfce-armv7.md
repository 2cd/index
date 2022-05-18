# arch-xfce-armv7

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
    --name arch-xfce-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-armv7 zsh
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

## arch-xfce-armv7.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-05-18"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2022-05-18_01-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d1cb7b183ffa336637fe06e82eb560a4d411b53a5455688c96b39add01b2c7d9"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3520472064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1126822112

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220511"
previous_tag = "2022-05-11"
previous_file = "arch-xfce_armhf_2022-05-11_01-01-rootfs.tar.zst"
previous_sha256 = "b77b8e4cb4529c8e058a43393e5304fbb6be77ffebace0ea245d0fa3f55fee0e"

current_version = "latest02"
current_date = "20220518"
old_file = "arch-xfce_armhf_2022-05-04_00-59-rootfs.tar.zst"
old_sha256 = "1c6469056c871c8fc3841bfa082c3a325a2e8efe1a075e8c276ca048265655de"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2022-05-18_01-01-rootfs.tar.zst
# SHA256SUM=d1cb7b183ffa336637fe06e82eb560a4d411b53a5455688c96b39add01b2c7d9
# BUILD_DATE=20220518
# BUILD_TAG=2022-05-18
# STATUS=completed
# VERSION=latest02
# END_TIME=01:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-18
begin = 2022-05-18 00:27:20.690860584+00:00
start-sync_0 = 00:42:57
start-zstd = 00:46:23
start-sync_1 = 01:00:08
end-sync_1 = 01:01:26
end = 2022-05-18 01:01:26.954787088+00:00

[server]
repo = "cake233/arch-xfce-armv7"

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
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
