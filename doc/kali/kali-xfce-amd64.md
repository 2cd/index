# kali-xfce-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name kali-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-amd64 zsh
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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2023-02-23"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2023-02-23_12-53.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c9c7c302153778adf574b148ceb9b0919513dcfaa644e3f0986ca253e830c489"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4344922624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1227888311

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230216"
previous_tag = "2023-02-16"
previous_file = "kali-xfce_amd64_2023-02-16_13-02-rootfs.tar.zst"
previous_sha256 = "c1746f05bec28f19575970d9f014c8d64ef4aac1ee20da6b6aae58e465a6b2c7"

current_version = "latest02"
current_date = "20230223"
old_file = "kali-xfce_amd64_2023-02-09_12-58-rootfs.tar.zst"
old_sha256 = "6a724a72a8743629d55428b4174a4d662140c5a2447618648defee07b1cd25a7"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2023-02-23_12-53-rootfs.tar.zst
# SHA256SUM=c9c7c302153778adf574b148ceb9b0919513dcfaa644e3f0986ca253e830c489
# BUILD_DATE=20230223
# BUILD_TAG=2023-02-23
# STATUS=completed
# VERSION=latest02
# END_TIME=12:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-23
begin = 2023-02-23 12:24:57.204181433+00:00
start-sync_0 = 12:33:07
start-zstd = 12:36:56
start-sync_1 = 12:52:18
end-sync_1 = 12:53:44
end = 2023-02-23 12:53:44.745058828+00:00

[server]
repo = "cake233/kali-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
