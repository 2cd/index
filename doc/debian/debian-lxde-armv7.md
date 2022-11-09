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
tag = ["lxde", "2022-11-09"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2022-11-09_13-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8a63cb0e3bed38c11e938c614af350109e7418ae0339b280d9db04e60969b274"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3146827776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "934M"
zstd_bytes = 979031792

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221102"
previous_tag = "2022-11-02"
previous_file = "debian-lxde_armhf_2022-11-02_12-48-rootfs.tar.zst"
previous_sha256 = "fb00392d3f78745c54cd39ff864ebf2487d35d390a4b4e796855a237759bc118"

current_version = "latest01"
current_date = "20221109"
old_file = "debian-lxde_armhf_2022-10-26_12-56-rootfs.tar.zst"
old_sha256 = "67283fd9cae0d2bef0909e7df73054521f9654112e9852e346bc5bdacf622312"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-11-09_13-02-rootfs.tar.zst
# SHA256SUM=8a63cb0e3bed38c11e938c614af350109e7418ae0339b280d9db04e60969b274
# BUILD_DATE=20221109
# BUILD_TAG=2022-11-09
# STATUS=completed
# VERSION=latest01
# END_TIME=13:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-09
begin = 2022-11-09 12:18:52.843126940+00:00
start-sync_0 = 12:48:22
start-zstd = 12:50:50
start-sync_1 = 13:01:03
end-sync_1 = 13:02:14
end = 2022-11-09 13:02:14.984252194+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-4) 2.36'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
