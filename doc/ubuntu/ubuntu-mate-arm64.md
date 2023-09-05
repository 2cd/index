# ubuntu-mate-arm64

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
    --name ubuntu-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-mate-arm64 zsh
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

## ubuntu-mate-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["mate", "2023-09-05", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-mate_arm64_2023-09-05_01-27.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6d41923bfaa171f7f96932b949a8adc962548978d4a6b49b89ab5ef794793db4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.8G"
tar_bytes = 5147213312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1355976098

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230829"
previous_tag = "2023-08-29"
previous_file = "ubuntu-mate_arm64_2023-08-29_01-36-rootfs.tar.zst"
previous_sha256 = "f6e67d1db11dc5506858467271bf17a4d9ecbf187cbc4c2f8cf144059d043465"

current_version = "latest02"
current_date = "20230905"
old_file = "ubuntu-mate_arm64_2023-08-22_01-22-rootfs.tar.zst"
old_sha256 = "71e422cac8939ab102add48cf75d0b49463f2d7c353412a370a136fd77865462"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-mate_arm64_2023-09-05_01-27-rootfs.tar.zst
# SHA256SUM=6d41923bfaa171f7f96932b949a8adc962548978d4a6b49b89ab5ef794793db4
# BUILD_DATE=20230905
# BUILD_TAG=2023-09-05
# STATUS=completed
# VERSION=latest02
# END_TIME=01:27

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-05
begin = 2023-09-05 00:28:26.831765809+00:00
start-sync_0 = 01:04:12
start-zstd = 01:08:40
start-sync_1 = 01:25:34
end-sync_1 = 01:27:03
end = 2023-09-05 01:27:03.746568802+00:00

[server]
repo = "cake233/ubuntu-mate-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu4) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
