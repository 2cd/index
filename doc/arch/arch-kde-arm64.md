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
tag = ["kde", "2023-04-12"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_arm64_2023-04-12_01-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "447e4381946dd3cc8954d099b84cd1d31c2a4870d236394b022f1afb64146a78"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.1G"
tar_bytes = 5410581504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1575119024

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230405"
previous_tag = "2023-04-05"
previous_file = "arch-kde_arm64_2023-04-05_01-27-rootfs.tar.zst"
previous_sha256 = "a0ba4ffd542e051b4aee4b0d5e8ab85966d0b5e171f1dda2289a8fe3fefce759"

current_version = "latest01"
current_date = "20230412"
old_file = "arch-kde_arm64_2023-03-22_01-32-rootfs.tar.zst"
old_sha256 = "fa4266918d35be50c6a5b27104b9d8e94cdad386cd3b464696017a5abce146a0"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2023-04-12_01-20-rootfs.tar.zst
# SHA256SUM=447e4381946dd3cc8954d099b84cd1d31c2a4870d236394b022f1afb64146a78
# BUILD_DATE=20230412
# BUILD_TAG=2023-04-12
# STATUS=completed
# VERSION=latest01
# END_TIME=01:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-12
begin = 2023-04-12 00:28:53.379786514+00:00
start-sync_0 = 00:54:45
start-zstd = 00:59:44
start-sync_1 = 01:19:09
end-sync_1 = 01:20:41
end = 2023-04-12 01:20:41.821372712+00:00

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
