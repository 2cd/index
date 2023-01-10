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
tag = ["lxqt", "2023-01-10", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-01-10_00-34.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "121b64c1c312d99a95215c382e8235395a645091c33b019294092a0908856522"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4008493056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1082513943

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230103"
previous_tag = "2023-01-03"
previous_file = "ubuntu-lxqt_amd64_2023-01-03_00-27-rootfs.tar.zst"
previous_sha256 = "4b677fa3dad2967b01ea4b750013d4bd7cd32bb0b69c72982e66493d6472b9a0"

current_version = "latest02"
current_date = "20230110"
old_file = "ubuntu-lxqt_amd64_2022-12-27_00-28-rootfs.tar.zst"
old_sha256 = "c7592e665c2106ed3111540856d56eb139ebe3f11d76e95e1a9a02d80d40b736"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-01-10_00-34-rootfs.tar.zst
# SHA256SUM=121b64c1c312d99a95215c382e8235395a645091c33b019294092a0908856522
# BUILD_DATE=20230110
# BUILD_TAG=2023-01-10
# STATUS=completed
# VERSION=latest02
# END_TIME=00:34

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-10
begin = 2023-01-10 00:03:00.455703933+00:00
start-sync_0 = 00:11:31
start-zstd = 00:15:53
start-sync_1 = 00:33:36
end-sync_1 = 00:34:53
end = 2023-01-10 00:34:53.905331613+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
