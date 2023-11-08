# debian-xfce-arm64

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
    --name debian-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-arm64 zsh
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

## debian-xfce-arm64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2023-11-08"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_arm64_2023-11-08_13-52.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b719887430e7cbef2029122fbd946f05d58e39adcedc124993bf191a50de4211"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4899612160

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1308083374

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231025"
previous_tag = "2023-10-25"
previous_file = "debian-xfce_arm64_2023-10-25_14-59-rootfs.tar.zst"
previous_sha256 = "fc23a86a7a5ed98ff7cd9f808ca428d4ddacb0c08efd63706245dc456fa531df"

current_version = "latest02"
current_date = "20231108"
old_file = "debian-xfce_arm64_2023-10-18_14-49-rootfs.tar.zst"
old_sha256 = "10ff464b54dcfd91c44d025d47c29806d63e7600f386734bd4d4b6e8016f8d13"
# edition 2021
# DISTRO_NAME=debian-sid_arm64
# ROOTFS_FILE=debian-xfce_arm64_2023-11-08_13-52-rootfs.tar.zst
# SHA256SUM=b719887430e7cbef2029122fbd946f05d58e39adcedc124993bf191a50de4211
# BUILD_DATE=20231108
# BUILD_TAG=2023-11-08
# STATUS=completed
# VERSION=latest02
# END_TIME=13:52

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-08
begin = 2023-11-08 12:31:28.089192145+00:00
start-sync_0 = 13:36:32
start-zstd = 13:39:02
start-sync_1 = 13:51:07
end-sync_1 = 13:52:35
end = 2023-11-08 13:52:35.170520055+00:00

[server]
repo = "cake233/debian-xfce-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
