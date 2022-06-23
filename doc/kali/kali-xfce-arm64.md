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
tag = ["xfce", "2022-06-23"]
os = "kali"
release = "rolling"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_arm64_2022-06-23_13-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "aff0e9646399bcb68cc97a42fbf7e9b54d53aa34ff37a748084f711630c29aee"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.3G"
tar_bytes = 6668571136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1814957379

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220616"
previous_tag = "2022-06-16"
previous_file = "kali-xfce_arm64_2022-06-16_13-55-rootfs.tar.zst"
previous_sha256 = "08bed41bad60d12b343b18e9bc60cd970131fddef413176424a1666e0c092aa8"

current_version = "latest02"
current_date = "20220623"
old_file = "kali-xfce_arm64_2022-06-09_13-55-rootfs.tar.zst"
old_sha256 = "49ada6a8c46e3043ad27dda2dd767cb0c5a367afdd8cd6c7006244b8bfadf457"
# edition 2021
# DISTRO_NAME=kali-rolling_arm64
# ROOTFS_FILE=kali-xfce_arm64_2022-06-23_13-41-rootfs.tar.zst
# SHA256SUM=aff0e9646399bcb68cc97a42fbf7e9b54d53aa34ff37a748084f711630c29aee
# BUILD_DATE=20220623
# BUILD_TAG=2022-06-23
# STATUS=completed
# VERSION=latest02
# END_TIME=13:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-23
begin = 2022-06-23 12:18:36.701051639+00:00
start-sync_0 = 13:10:51
start-zstd = 13:17:16
start-sync_1 = 13:39:27
end-sync_1 = 13:41:15
end = 2022-06-23 13:41:15.055979688+00:00

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
