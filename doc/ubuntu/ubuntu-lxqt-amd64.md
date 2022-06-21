# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2022-06-21", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2022-06-21_00-41.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f9c9b38028521e6ac11d507d5a015569a1718ec8d43dde818827cc597d101d75"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3838194688

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "976M"
zstd_bytes = 1023259304

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220614"
previous_tag = "2022-06-14"
previous_file = "ubuntu-lxqt_amd64_2022-06-14_00-45-rootfs.tar.zst"
previous_sha256 = "e17de6a810b7b3dbef9fe248e02ac85d9031c41e4774c7dcd6994fd000ee79a7"

current_version = "latest02"
current_date = "20220621"
old_file = "ubuntu-lxqt_amd64_2022-06-07_00-45-rootfs.tar.zst"
old_sha256 = "5dcab183562ae18415499d0054fdba5da60f435681bac49b8d84cc20ef00ea01"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2022-06-21_00-41-rootfs.tar.zst
# SHA256SUM=f9c9b38028521e6ac11d507d5a015569a1718ec8d43dde818827cc597d101d75
# BUILD_DATE=20220621
# BUILD_TAG=2022-06-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-21
begin = 2022-06-21 00:18:11.023446239+00:00
start-sync_0 = 00:24:08
start-zstd = 00:27:35
start-sync_1 = 00:40:32
end-sync_1 = 00:41:32
end = 2022-06-21 00:41:32.036565834+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
