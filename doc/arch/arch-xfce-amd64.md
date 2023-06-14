# arch-xfce-amd64

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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-amd64 zsh
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

## arch-xfce-amd64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2023-06-14"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_amd64_2023-06-14_01-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "449dc7d7c3b4444b1bbb120cbbb76954e5c6452eac53f4d891fecac4c07bcc91"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4018696192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1179233067

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230607"
previous_tag = "2023-06-07"
previous_file = "arch-xfce_amd64_2023-06-07_00-58-rootfs.tar.zst"
previous_sha256 = "8326b1ae94c21dc7a8a53430f9127a90f753cbe79ba4b51ce7dbc9974280666e"

current_version = "latest02"
current_date = "20230614"
old_file = "arch-xfce_amd64_2023-05-31_01-02-rootfs.tar.zst"
old_sha256 = "59f6ad8098dfc0b3e922965f12fad291a8e39ff497ac923e1a450e443f59e944"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2023-06-14_01-03-rootfs.tar.zst
# SHA256SUM=449dc7d7c3b4444b1bbb120cbbb76954e5c6452eac53f4d891fecac4c07bcc91
# BUILD_DATE=20230614
# BUILD_TAG=2023-06-14
# STATUS=completed
# VERSION=latest02
# END_TIME=01:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-14
begin = 2023-06-14 00:38:12.962726403+00:00
start-sync_0 = 00:43:32
start-zstd = 00:46:56
start-sync_1 = 01:02:40
end-sync_1 = 01:03:52
end = 2023-06-14 01:03:52.417389160+00:00

[server]
repo = "cake233/arch-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
