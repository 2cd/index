# arch-kde-amd64

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
    --name arch-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-amd64 zsh
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

## arch-kde-amd64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-02-16"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "arch-kde_amd64_2022-02-16_00-50.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2db38eff980db1b798f6434618a17bb6fd1e023cc266b2b332614a465bdc425a"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.3G"
tar_bytes = 4546577920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1452884289

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220209"
previous_tag = "2022-02-09"
previous_file = "arch-kde_amd64_2022-02-09_00-56-rootfs.tar.zst"
previous_sha256 = "3a6fe985c78875e66d1c59bcf2e2dfbd35d1d6f594bde931de81e325da2941c2"

current_version = "latest01"
current_date = "20220216"
old_file = "arch-kde_amd64_2022-02-02_00-55-rootfs.tar.zst"
old_sha256 = "a42b494f581244d287ad30ccb5836507a0b92a8fcaf2ec55bff082f07057b5f0"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2022-02-16_00-50-rootfs.tar.zst
# SHA256SUM=2db38eff980db1b798f6434618a17bb6fd1e023cc266b2b332614a465bdc425a
# BUILD_DATE=20220216
# BUILD_TAG=2022-02-16
# STATUS=completed
# VERSION=latest01
# END_TIME=00:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-16
begin = 2022-02-16 00:31:16.254818343+00:00
start-sync_0 = 00:36:48
start-zstd = 00:42:25
start-sync_1 = 00:49:07
end-sync_1 = 00:50:39
end = 2022-02-16 00:50:39.810562515+00:00

[server]
repo = "cake233/arch-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
