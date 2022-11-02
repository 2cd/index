# arch-mate-arm64

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
    --name arch-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-mate-arm64 zsh
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

## arch-mate-arm64.toml

```toml
[main]
name = "arch"
tag = ["mate", "2022-11-02"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-mate_arm64_2022-11-02_00-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "66ad8a9615f9126c9f16e3ab18fa868886bf544a413892cf8f7bf8008f15fb98"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5186332160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1449876670

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221026"
previous_tag = "2022-10-26"
previous_file = "arch-mate_arm64_2022-10-26_01-15-rootfs.tar.zst"
previous_sha256 = "524d063d0bc45a0381fa1081a2cd72fec01f4d3bbe42fc8ef14ad57618a633d6"

current_version = "latest01"
current_date = "20221102"
old_file = "arch-mate_arm64_2022-10-19_01-12-rootfs.tar.zst"
old_sha256 = "696431bbd9bd5d09043de3fa6c2a33b55e4f433e3c3a5445072291aa50fe07d7"
# edition 2021
# DISTRO_NAME=arch_arm64
# ROOTFS_FILE=arch-mate_arm64_2022-11-02_00-49-rootfs.tar.zst
# SHA256SUM=66ad8a9615f9126c9f16e3ab18fa868886bf544a413892cf8f7bf8008f15fb98
# BUILD_DATE=20221102
# BUILD_TAG=2022-11-02
# STATUS=completed
# VERSION=latest01
# END_TIME=00:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-02
begin = 2022-11-02 00:08:52.171169849+00:00
start-sync_0 = 00:27:12
start-zstd = 00:31:48
start-sync_1 = 00:47:56
end-sync_1 = 00:49:16
end = 2022-11-02 00:49:16.637913478+00:00

[server]
repo = "cake233/arch-mate-arm64"

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
