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
tag = ["lxqt", "2023-10-10", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-10-10_01-51.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2af6e0aa166a0ad152de3b1c3a36baad8fcf32e2a8e1f55751536ee24a2ef009"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4901710848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1289679400

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231003"
previous_tag = "2023-10-03"
previous_file = "ubuntu-lxqt_arm64_2023-10-03_01-34-rootfs.tar.zst"
previous_sha256 = "e73bf5542d05a5ecb33bbb9498ac5a623e6b518ad7e85007cf978ff28eda73e6"

current_version = "latest01"
current_date = "20231010"
old_file = "ubuntu-lxqt_arm64_2023-09-26_01-35-rootfs.tar.zst"
old_sha256 = "a669858390f1282496150c72ec4ab942b777135184de25dfe284f1cdeaf3976f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-10-10_01-51-rootfs.tar.zst
# SHA256SUM=2af6e0aa166a0ad152de3b1c3a36baad8fcf32e2a8e1f55751536ee24a2ef009
# BUILD_DATE=20231010
# BUILD_TAG=2023-10-10
# STATUS=completed
# VERSION=latest01
# END_TIME=01:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-10
begin = 2023-10-10 00:29:40.129491068+00:00
start-sync_0 = 01:27:20
start-zstd = 01:31:42
start-sync_1 = 01:49:47
end-sync_1 = 01:51:23
end = 2023-10-10 01:51:23.106975259+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
