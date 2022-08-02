# fedora-mate-arm64

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
    --name fedora-mate-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-arm64 zsh
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

## fedora-mate-arm64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2022-08-02"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2022-08-02_14-55.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9740177dec1ee5e39aaac1f01144ac0cf62aba8cf1ac031928ddebee7aacbb12"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.0G"
tar_bytes = 6407022592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1719731309

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "fedora-mate_arm64_2022-07-12_14-16-rootfs.tar.zst"
previous_sha256 = "a95f15ba7a976d22d21c5a62a6a0a6b9b6d0fde2071b07d8e206c65da8a21c27"

current_version = "latest01"
current_date = "20220802"
old_file = "fedora-mate_arm64_2022-07-05_14-07-rootfs.tar.zst"
old_sha256 = "f2c61f621623f42204fbbfabbf4b641de43a6983d36c7c9d3477ecd62bbcd14b"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-08-02_14-55-rootfs.tar.zst
# SHA256SUM=9740177dec1ee5e39aaac1f01144ac0cf62aba8cf1ac031928ddebee7aacbb12
# BUILD_DATE=20220802
# BUILD_TAG=2022-08-02
# STATUS=completed
# VERSION=latest01
# END_TIME=14:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-02
begin = 2022-08-02 12:50:12.138922199+00:00
start-sync_0 = 14:24:19
start-zstd = 14:30:07
start-sync_1 = 14:53:20
end-sync_1 = 14:55:21
end = 2022-08-02 14:55:21.738218105+00:00

[server]
repo = "cake233/fedora-mate-arm64"

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
