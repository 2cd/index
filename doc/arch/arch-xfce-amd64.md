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
tag = ["xfce", "2022-11-21"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-xfce_amd64_2022-11-21_06-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9829e89034bf4914e3c0e25dfb1b629f472055ecee5e2a5aee218519f6834bbe"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3889659904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1169450413

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221116"
previous_tag = "2022-11-16"
previous_file = "arch-xfce_amd64_2022-11-16_00-32-rootfs.tar.zst"
previous_sha256 = "68a841d6cd0a05eca4c6886fcc191acbfabe0c5f309ea32938273362693247cc"

current_version = "latest02"
current_date = "20221121"
old_file = "arch-xfce_amd64_2022-11-09_01-43-rootfs.tar.zst"
old_sha256 = "1378c1983ac85ae3c454a723ce7001a216b866680c0090e572655a9565e006f3"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2022-11-21_06-30-rootfs.tar.zst
# SHA256SUM=9829e89034bf4914e3c0e25dfb1b629f472055ecee5e2a5aee218519f6834bbe
# BUILD_DATE=20221121
# BUILD_TAG=2022-11-21
# STATUS=completed
# VERSION=latest02
# END_TIME=06:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-21
begin = 2022-11-21 06:01:20.523945395+00:00
start-sync_0 = 06:07:02
start-zstd = 06:11:16
start-sync_1 = 06:29:30
end-sync_1 = 06:30:53
end = 2022-11-21 06:30:53.380186777+00:00

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
ldd = 'ldd (GNU libc) 2.36'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
