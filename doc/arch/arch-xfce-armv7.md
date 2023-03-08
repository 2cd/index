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
tag = ["xfce", "2023-03-08"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_armhf_2023-03-08_01-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f326c50a70e7a810578ee6fc436c75e47ce9b95b78d6bdef0cf0bcea9964d73d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.2G"
tar_bytes = 3405667840

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1114500333

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230301"
previous_tag = "2023-03-01"
previous_file = "arch-xfce_armhf_2023-03-01_01-09-rootfs.tar.zst"
previous_sha256 = "f249794b224506f9eea5b9839bfc20e3f8d773724ab1113b2c62f0364914bd89"

current_version = "latest01"
current_date = "20230308"
old_file = "arch-xfce_armhf_2023-02-22_01-12-rootfs.tar.zst"
old_sha256 = "000106e0c7601f10673dc8a4955917db588905cc2027d8eff5ea59250cfae07c"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-xfce_armhf_2023-03-08_01-02-rootfs.tar.zst
# SHA256SUM=f326c50a70e7a810578ee6fc436c75e47ce9b95b78d6bdef0cf0bcea9964d73d
# BUILD_DATE=20230308
# BUILD_TAG=2023-03-08
# STATUS=completed
# VERSION=latest01
# END_TIME=01:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-08
begin = 2023-03-08 00:30:35.378495541+00:00
start-sync_0 = 00:45:18
start-zstd = 00:48:12
start-sync_1 = 01:00:57
end-sync_1 = 01:02:19
end = 2023-03-08 01:02:19.461286006+00:00

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
