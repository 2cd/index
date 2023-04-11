# ubuntu-kde-amd64

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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-04-11", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2023-04-11_00-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "85188b25dacb7e2488527638a8c00bef0e201fb876c3c2a8f27f3a597ff7deca"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4731081728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1313298824

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230404"
previous_tag = "2023-04-04"
previous_file = "ubuntu-kde_amd64_2023-04-04_00-37-rootfs.tar.zst"
previous_sha256 = "62b157b392a58d236437f0aa721ca28d9d28711b514bdfbb0de4e88f75df8686"

current_version = "latest01"
current_date = "20230411"
old_file = "ubuntu-kde_amd64_2023-03-28_00-35-rootfs.tar.zst"
old_sha256 = "9c6cf7348e116a368593516030eb083dccfac1ce30bf39dba09cb96a5a5eb133"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2023-04-11_00-37-rootfs.tar.zst
# SHA256SUM=85188b25dacb7e2488527638a8c00bef0e201fb876c3c2a8f27f3a597ff7deca
# BUILD_DATE=20230411
# BUILD_TAG=2023-04-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-11
begin = 2023-04-11 00:02:59.264158031+00:00
start-sync_0 = 00:11:06
start-zstd = 00:16:13
start-sync_1 = 00:36:22
end-sync_1 = 00:37:50
end = 2023-04-11 00:37:50.141414099+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
