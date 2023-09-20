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
tag = ["kde", "2023-09-20"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2023-09-20_01-29.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3e98bd3eea03e8cdefe116026769b6ec58281742ea17aa590aaceaa0e6aed9c7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5440243712

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1583301655

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230913"
previous_tag = "2023-09-13"
previous_file = "arch-kde_arm64_2023-09-13_01-38-rootfs.tar.zst"
previous_sha256 = "f8c1c0490b4e19759965355559886d54fc8dd2c6d4fa49805bf2cbc646621747"

current_version = "latest02"
current_date = "20230920"
old_file = "arch-kde_arm64_2023-09-06_01-24-rootfs.tar.zst"
old_sha256 = "e05d4466f1eddd7b96fa8ed889d9ac94b76cb570c8eba78eed00b0c9573dcbf7"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2023-09-20_01-29-rootfs.tar.zst
# SHA256SUM=3e98bd3eea03e8cdefe116026769b6ec58281742ea17aa590aaceaa0e6aed9c7
# BUILD_DATE=20230920
# BUILD_TAG=2023-09-20
# STATUS=completed
# VERSION=latest02
# END_TIME=01:29

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-20
begin = 2023-09-20 00:49:54.827661687+00:00
start-sync_0 = 01:03:39
start-zstd = 01:08:42
start-sync_1 = 01:28:15
end-sync_1 = 01:29:49
end = 2023-09-20 01:29:49.944843274+00:00

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
