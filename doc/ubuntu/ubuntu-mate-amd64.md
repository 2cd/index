# ubuntu-mate-amd64

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
    --name ubuntu-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-amd64 zsh
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

## ubuntu-mate-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-11-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_amd64_2023-11-07_00-56.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fd398316f729aace15d0295a9671c3e0d84fc37584c7642e58ef0e9f31ed0b91"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.2G"
tar_bytes = 4487370752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1208894776

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231024"
previous_tag = "2023-10-24"
previous_file = "ubuntu-mate_amd64_2023-10-24_00-59-rootfs.tar.zst"
previous_sha256 = "44de9440de7e8637c74042cb9b3d80f3f1ab9d834b7efe35773408bea79e8f55"

current_version = "latest02"
current_date = "20231107"
old_file = "ubuntu-mate_amd64_2023-10-17_01-01-rootfs.tar.zst"
old_sha256 = "20730b3ae3dec8fbb57e9487e85b6bca2754171d98499bdf948d1ad5f04daab5"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-mate_amd64_2023-11-07_00-56-rootfs.tar.zst
# SHA256SUM=fd398316f729aace15d0295a9671c3e0d84fc37584c7642e58ef0e9f31ed0b91
# BUILD_DATE=20231107
# BUILD_TAG=2023-11-07
# STATUS=completed
# VERSION=latest02
# END_TIME=00:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-07
begin = 2023-11-07 00:24:17.273119969+00:00
start-sync_0 = 00:31:36
start-zstd = 00:36:00
start-sync_1 = 00:54:40
end-sync_1 = 00:56:09
end = 2023-11-07 00:56:09.145470814+00:00

[server]
repo = "cake233/ubuntu-mate-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
