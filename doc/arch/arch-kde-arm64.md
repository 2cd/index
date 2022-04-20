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
tag = ["kde", "2022-04-20"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "arch-kde_arm64_2022-04-20_01-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c6d326d8b8943b629191c67ec0bc7a61f024a8d84bad02949906291a15418950"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5189096960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1464033494

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220413"
previous_tag = "2022-04-13"
previous_file = "arch-kde_arm64_2022-04-13_01-25-rootfs.tar.zst"
previous_sha256 = "dfec0348ed2839fd78ee43c29e56a3635b9ccda57076ae77619f0ddbee601442"

current_version = "latest02"
current_date = "20220420"
old_file = "arch-kde_arm64_2022-03-30_00-13-rootfs.tar.zst"
old_sha256 = "30f2f49629217d9421e3068dd81a582a7a300a1059950f8fe565174eab3d0b73"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-kde_arm64_2022-04-20_01-09-rootfs.tar.zst
# SHA256SUM=c6d326d8b8943b629191c67ec0bc7a61f024a8d84bad02949906291a15418950
# BUILD_DATE=20220420
# BUILD_TAG=2022-04-20
# STATUS=completed
# VERSION=latest02
# END_TIME=01:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-20
begin = 2022-04-20 00:25:53.061207332+00:00
start-sync_0 = 00:45:49
start-zstd = 00:50:54
start-sync_1 = 01:08:31
end-sync_1 = 01:09:56
end = 2022-04-20 01:09:56.304001586+00:00

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
zsh = 'zsh 5.8.1 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
