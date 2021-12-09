# kali-xfce-armv7

## How to run it?

```shell
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

```shell
    docker exex -it kali-xfce-armv7 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```shell
    startvnc
```

or

```shell
    startx11vnc
```

or

```shell
    novnc
```

Note:

If you want to use novnc, then open your browser, and type the address:

```
localhost:36081
```

If you want to use tiger/x11vnc, then open vnc viewer, then type the address:

```
localhost:5903
```

## kali-xfce-armv7.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2021-12-09"]
os = "kali"
release = "rolling"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "kali-xfce_armhf_2021-12-09_13-35.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2913feeb9e1cc6a8dea72543caf148a3dee24f332fddc28a4d5e5b72533d1a88"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4815214080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1596900783

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211202"
previous_tag = "2021-12-02"
previous_file = "kali-xfce_armhf_2021-12-02_09-03-rootfs.tar.zst"
previous_sha256 = ""

current_version = "latest01"
current_date = "20211209"
old_file = "kali-xfce_armhf_2021-11-30_16-33-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=kali-rolling_armhf
# ROOTFS_FILE=kali-xfce_armhf_2021-12-09_13-35-rootfs.tar.zst
# SHA256SUM=2913feeb9e1cc6a8dea72543caf148a3dee24f332fddc28a4d5e5b72533d1a88
# BUILD_DATE=20211209
# BUILD_TAG=2021-12-09
# STATUS=completed
# VERSION=latest01
# END_TIME=13:35

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-09
begin = 2021-12-09 12:19:35.411687085+00:00
start-sync_0 = 13:17:41
start-zstd = 13:22:43
start-sync_1 = 13:33:52
end-sync_1 = 13:35:28
end = 2021-12-09 13:35:28.285747835+00:00

[server]
repo = "cake233/kali-xfce-armv7"

[server.node1]
name = "cn"
current = false
previous = true
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
zsh = 'zsh 5.8 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
