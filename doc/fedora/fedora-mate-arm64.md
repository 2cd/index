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
tag = ["mate", "2022-03-22"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = true

[file]
name = "fedora-mate_arm64_2022-03-22_13-44.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "306e8e4da76735b3edb45c9da46d6cde0922e2a9e7f0965e7ba35b5559b54eec"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.6G"
tar_bytes = 2733001216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "677M"
zstd_bytes = 709093624

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220315"
previous_tag = "2022-03-15"
previous_file = "fedora-mate_arm64_2022-03-15_14-44-rootfs.tar.zst"
previous_sha256 = "d845dbf7297d118a640d48b9d17a04fa0ea7d22a823f93145e271fba23430adf"

current_version = "latest02"
current_date = "20220322"
old_file = "fedora-mate_arm64_2022-03-08_13-58-rootfs.tar.zst"
old_sha256 = "f9a448dee0f487d4908e90da38a77d5dc84193208f7ff90f38cfd2625355d0a4"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2022-03-22_13-44-rootfs.tar.zst
# SHA256SUM=306e8e4da76735b3edb45c9da46d6cde0922e2a9e7f0965e7ba35b5559b54eec
# BUILD_DATE=20220322
# BUILD_TAG=2022-03-22
# STATUS=completed
# VERSION=latest02
# END_TIME=13:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-22
begin = 2022-03-22 12:37:57.538023031+00:00
start-sync_0 = 13:34:10
start-zstd = 13:36:01
start-sync_1 = 13:43:26
end-sync_1 = 13:44:14
end = 2022-03-22 13:44:14.344625765+00:00

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
ldd = 'ldd (GNU libc) 2.35.9000'
zsh = 'zsh 5.8.1 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
