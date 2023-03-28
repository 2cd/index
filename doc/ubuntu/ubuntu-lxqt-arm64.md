# ubuntu-lxqt-arm64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not arm64, then install qemu & binfmt-support.
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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-03-28", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-03-28_01-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2ccbe62c3167a19e5474e8b517038764d0f18feefd55c753ee5cec8669693249"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4233340416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1146182754

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230321"
previous_tag = "2023-03-21"
previous_file = "ubuntu-lxqt_arm64_2023-03-21_00-57-rootfs.tar.zst"
previous_sha256 = "ad7b498c459304c7d2f9d6cf7fd07690a49e87a1a49f86b3d36229802cbf0fd0"

current_version = "latest01"
current_date = "20230328"
old_file = "ubuntu-lxqt_arm64_2023-03-14_00-56-rootfs.tar.zst"
old_sha256 = "9c0cbb9a21f066b690d6c799714fa5b830eaac12df2ae912fb1c524e56b7b389"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-03-28_01-12-rootfs.tar.zst
# SHA256SUM=2ccbe62c3167a19e5474e8b517038764d0f18feefd55c753ee5cec8669693249
# BUILD_DATE=20230328
# BUILD_TAG=2023-03-28
# STATUS=completed
# VERSION=latest01
# END_TIME=01:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-28
begin = 2023-03-28 00:03:13.329551079+00:00
start-sync_0 = 00:49:25
start-zstd = 00:53:31
start-sync_1 = 01:11:18
end-sync_1 = 01:12:36
end = 2023-03-28 01:12:36.635971051+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
