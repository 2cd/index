# kali-xfce-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name kali-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-arm64 zsh
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

## kali-xfce-arm64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-06-16"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2022-06-16_13-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "08bed41bad60d12b343b18e9bc60cd970131fddef413176424a1666e0c092aa8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.4G"
tar_bytes = 5797698560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1650488275

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220609"
previous_tag = "2022-06-09"
previous_file = "kali-xfce_arm64_2022-06-09_13-55-rootfs.tar.zst"
previous_sha256 = "49ada6a8c46e3043ad27dda2dd767cb0c5a367afdd8cd6c7006244b8bfadf457"

current_version = "latest01"
current_date = "20220616"
old_file = "kali-xfce_arm64_2022-06-02_13-46-rootfs.tar.zst"
old_sha256 = "dd63d36d17c48d98e79aa73c5a57636f0319d9a442001157a2283a1826d9666a"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-06-16_13-55-rootfs.tar.zst
# SHA256SUM=08bed41bad60d12b343b18e9bc60cd970131fddef413176424a1666e0c092aa8
# BUILD_DATE=20220616
# BUILD_TAG=2022-06-16
# STATUS=completed
# VERSION=latest01
# END_TIME=13:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-16
begin = 2022-06-16 12:18:57.736193250+00:00
start-sync_0 = 13:22:58
start-zstd = 13:30:00
start-sync_1 = 13:53:09
end-sync_1 = 13:55:05
end = 2022-06-16 13:55:05.057702903+00:00

[server]
repo = "cake233/kali-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.33-6) 2.33'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
