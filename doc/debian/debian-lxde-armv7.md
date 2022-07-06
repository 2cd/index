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
tag = ["lxde", "2022-07-06"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2022-07-06_12-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "513ccaf1b18b3db1565066120678b1b1a62c343e26ddd7b6839b52f97418279b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.9G"
tar_bytes = 3048884736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "934M"
zstd_bytes = 978654747

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220629"
previous_tag = "2022-06-29"
previous_file = "debian-lxde_armhf_2022-06-29_13-08-rootfs.tar.zst"
previous_sha256 = "c1e16089984231e75ed664f8dbc2ca4657fbe380e2a031a94893aeafc69ba81c"

current_version = "latest02"
current_date = "20220706"
old_file = "debian-lxde_armhf_2022-06-22_13-05-rootfs.tar.zst"
old_sha256 = "1b1ee33eb613f8e827fe44d4d576efdc46f82a83dcffa019b7dd8a34ac7fe2fc"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-07-06_12-55-rootfs.tar.zst
# SHA256SUM=513ccaf1b18b3db1565066120678b1b1a62c343e26ddd7b6839b52f97418279b
# BUILD_DATE=20220706
# BUILD_TAG=2022-07-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-06
begin = 2022-07-06 12:19:41.252422755+00:00
start-sync_0 = 12:42:48
start-zstd = 12:44:53
start-sync_1 = 12:54:03
end-sync_1 = 12:55:01
end = 2022-07-06 12:55:01.759433070+00:00

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
