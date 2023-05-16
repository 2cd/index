# fedora-kde-arm64

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
    --name fedora-kde-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-arm64 zsh
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

## fedora-kde-arm64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2023-05-16"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_arm64_2023-05-16_15-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f3a84e56fafb0e79391b4228c4cd35bf8eeb20a350a4742fec73e246f05031b2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.9G"
tar_bytes = 7396280832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.8G"
zstd_bytes = 1919946210

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230502"
previous_tag = "2023-05-02"
previous_file = "fedora-kde_arm64_2023-05-02_15-19-rootfs.tar.zst"
previous_sha256 = "973ace07980cd97020227196f8121dcd46796a46d9cdb1ef652eaf397e42800d"

current_version = "latest02"
current_date = "20230516"
old_file = "fedora-kde_arm64_2023-04-25_15-10-rootfs.tar.zst"
old_sha256 = "1e078314f0fe091ea271b669174c67fc11b79593381113494088780adbae4d41"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-kde_arm64_2023-05-16_15-10-rootfs.tar.zst
# SHA256SUM=f3a84e56fafb0e79391b4228c4cd35bf8eeb20a350a4742fec73e246f05031b2
# BUILD_DATE=20230516
# BUILD_TAG=2023-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=15:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-16
begin = 2023-05-16 13:03:22.216228922+00:00
start-sync_0 = 14:42:12
start-zstd = 14:47:18
start-sync_1 = 15:08:25
end-sync_1 = 15:10:20
end = 2023-05-16 15:10:20.262816416+00:00

[server]
repo = "cake233/fedora-kde-arm64"

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
