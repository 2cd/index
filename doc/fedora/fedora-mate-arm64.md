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
tag = ["mate", "2023-06-20"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_arm64_2023-06-20_15-35.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e82a8adf6f9361e66607d5deb088402fea3ccacd2a504ad798e3708832081c4e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.7G"
tar_bytes = 7143550464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.7G"
zstd_bytes = 1747690305

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230613"
previous_tag = "2023-06-13"
previous_file = "fedora-mate_arm64_2023-06-13_15-08-rootfs.tar.zst"
previous_sha256 = "0670265f67d5e6f6f9dfbea9481d82dd6015addc88518db03b9817009f94a99d"

current_version = "latest01"
current_date = "20230620"
old_file = "fedora-mate_arm64_2023-06-06_14-18-rootfs.tar.zst"
old_sha256 = "b3c7acf8ec7493c20cb8e98e78ab5356dec0d5dc9cc3ce5414d7462e72392f07"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-mate_arm64_2023-06-20_15-35-rootfs.tar.zst
# SHA256SUM=e82a8adf6f9361e66607d5deb088402fea3ccacd2a504ad798e3708832081c4e
# BUILD_DATE=20230620
# BUILD_TAG=2023-06-20
# STATUS=completed
# VERSION=latest01
# END_TIME=15:35

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-20
begin = 2023-06-20 12:51:50.723257656+00:00
start-sync_0 = 15:01:46
start-zstd = 15:08:14
start-sync_1 = 15:33:35
end-sync_1 = 15:35:41
end = 2023-06-20 15:35:41.653696229+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
