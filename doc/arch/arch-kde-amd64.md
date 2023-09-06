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

## arch-kde-amd64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2023-09-06"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2023-09-06_01-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e73021d45f2ccd80846125657e8379fc9932aed197ede750d335e683b733f913"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4881787904

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1456446377

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230830"
previous_tag = "2023-08-30"
previous_file = "arch-kde_amd64_2023-08-30_01-20-rootfs.tar.zst"
previous_sha256 = "6290145f7b5fe51f0bdec8a5263a9994b783de5ae54f9eb709c9f0a22154b41a"

current_version = "latest02"
current_date = "20230906"
old_file = "arch-kde_amd64_2023-08-09_01-11-rootfs.tar.zst"
old_sha256 = "09a348c0fa584521e102d8ed22764f4dc075e26b5946424b5079357acc12e586"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2023-09-06_01-14-rootfs.tar.zst
# SHA256SUM=e73021d45f2ccd80846125657e8379fc9932aed197ede750d335e683b733f913
# BUILD_DATE=20230906
# BUILD_TAG=2023-09-06
# STATUS=completed
# VERSION=latest02
# END_TIME=01:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-06
begin = 2023-09-06 00:44:01.921615010+00:00
start-sync_0 = 00:50:04
start-zstd = 00:54:53
start-sync_1 = 01:13:21
end-sync_1 = 01:14:51
end = 2023-09-06 01:14:51.389652447+00:00

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
ldd = 'ldd (GNU libc) 2.38'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
