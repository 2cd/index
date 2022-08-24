# arch-kde-arm64

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
    --name arch-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-arm64 zsh
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

## arch-kde-arm64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2022-08-24"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2022-08-24_01-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "88f1a34e7070e6806d9b65958fdeb21e85f26b163183357e94bd79468cff2504"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5317511680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1499388792

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220817"
previous_tag = "2022-08-17"
previous_file = "arch-kde_arm64_2022-08-17_01-22-rootfs.tar.zst"
previous_sha256 = "370d51928954d103b13b015cfb293cddbefe72d966ab3240bee7aacb79644621"

current_version = "latest01"
current_date = "20220824"
old_file = "arch-kde_arm64_2022-08-10_01-24-rootfs.tar.zst"
old_sha256 = "c8b39cfd943f129c1e015a3d376dae4e5a26278db0e17d8153835b7c08c5c59a"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2022-08-24_01-27-rootfs.tar.zst
# SHA256SUM=88f1a34e7070e6806d9b65958fdeb21e85f26b163183357e94bd79468cff2504
# BUILD_DATE=20220824
# BUILD_TAG=2022-08-24
# STATUS=completed
# VERSION=latest01
# END_TIME=01:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-24
begin = 2022-08-24 00:42:49.766707473+00:00
start-sync_0 = 01:02:39
start-zstd = 01:07:36
start-sync_1 = 01:26:10
end-sync_1 = 01:27:33
end = 2022-08-24 01:27:33.271619071+00:00

[server]
repo = "cake233/arch-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
