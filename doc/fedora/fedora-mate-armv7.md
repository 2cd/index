# fedora-mate-armv7

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
    --name fedora-mate-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-armv7 zsh
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

## fedora-mate-armv7.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-03-01"]
os = "fedora"
release = "rawhide"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "fedora-mate_armhf_2022-03-01_13-28.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "5300522f4229e66e9e955e38f56821953a324b9e74508fd552179183b9285480"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3173018624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1080379191

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220222"
previous_tag = "2022-02-22"
previous_file = "fedora-mate_armhf_2022-02-22_13-30-rootfs.tar.zst"
previous_sha256 = "4e9e637e98bcc8c2a0b518c3bca0bd78893ea88c3a478a06098de05644c60276"

current_version = "latest01"
current_date = "20220301"
old_file = "fedora-mate_armhf_2022-02-15_13-39-rootfs.tar.zst"
old_sha256 = "0239f4a3e2ff943d67f6029796cbfe19dfc9e17360ffced2b4d13b88d3297602"
# edition 2021
# DISTRO_NAME=fedora-rawhide_armhf
# ROOTFS_FILE=fedora-mate_armhf_2022-03-01_13-28-rootfs.tar.zst
# SHA256SUM=5300522f4229e66e9e955e38f56821953a324b9e74508fd552179183b9285480
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest01
# END_TIME=13:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 12:47:21.407808938+00:00
start-sync_0 = 13:15:50
start-zstd = 13:18:53
start-sync_1 = 13:27:03
end-sync_1 = 13:28:25
end = 2022-03-01 13:28:25.687666773+00:00

[server]
repo = "cake233/fedora-mate-armv7"

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
ldd = 'ldd (GNU libc) 2.34.9000'
zsh = 'zsh 5.8 (armv7hl-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
