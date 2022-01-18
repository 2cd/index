# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-01-18", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_amd64_2022-01-18_00-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7b8d1465886bfac9f1e256c9341dc802308ed3728758fdc1f8f8bd75a295d230"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2948315136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "743M"
zstd_bytes = 778514119

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220111"
previous_tag = "2022-01-11"
previous_file = "ubuntu-xfce_amd64_2022-01-11_00-39-rootfs.tar.zst"
previous_sha256 = "eb62ce0d4f18c827ede6ffc9dc198e7862830866f19086072a7b211c704d56b9"

current_version = "latest02"
current_date = "20220118"
old_file = "ubuntu-xfce_amd64_2022-01-04_00-38-rootfs.tar.zst"
old_sha256 = "6bb75267d4319568196c72df20cc8cb0f5b29ba902bbfc3549431ccaaefb70f0"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-01-18_00-40-rootfs.tar.zst
# SHA256SUM=7b8d1465886bfac9f1e256c9341dc802308ed3728758fdc1f8f8bd75a295d230
# BUILD_DATE=20220118
# BUILD_TAG=2022-01-18
# STATUS=completed
# VERSION=latest02
# END_TIME=00:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-18
begin = 2022-01-18 00:19:16.566905912+00:00
start-sync_0 = 00:26:26
start-zstd = 00:29:20
start-sync_1 = 00:39:14
end-sync_1 = 00:40:13
end = 2022-01-18 00:40:13.848835797+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
