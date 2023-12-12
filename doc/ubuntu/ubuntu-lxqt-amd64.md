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
tag = ["lxqt", "2023-12-12", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-12-12_00-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7c28a1162e8d8581b0e5a82cc2c5c88509b4cb9bb37e693e39d32a2bbb7b62b6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.1G"
tar_bytes = 4364103680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1177042887

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231128"
previous_tag = "2023-11-28"
previous_file = "ubuntu-lxqt_amd64_2023-11-28_00-47-rootfs.tar.zst"
previous_sha256 = "3e14b593bc41744bf3d95d18591be0bacbeb17bc19bed45ab4d9851f10c053b1"

current_version = "latest01"
current_date = "20231212"
old_file = "ubuntu-lxqt_amd64_2023-11-21_00-45-rootfs.tar.zst"
old_sha256 = "93b33f560f0252936173c8293ddb365653891bf206d79b53b6c52ddbd06f5b4d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-12-12_00-58-rootfs.tar.zst
# SHA256SUM=7c28a1162e8d8581b0e5a82cc2c5c88509b4cb9bb37e693e39d32a2bbb7b62b6
# BUILD_DATE=20231212
# BUILD_TAG=2023-12-12
# STATUS=completed
# VERSION=latest01
# END_TIME=00:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-12
begin = 2023-12-12 00:36:18.284197068+00:00
start-sync_0 = 00:43:10
start-zstd = 00:45:40
start-sync_1 = 00:57:53
end-sync_1 = 00:58:49
end = 2023-12-12 00:58:49.796026056+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-3ubuntu1) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
