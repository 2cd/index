# fedora-xfce-arm64

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
    --name fedora-xfce-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-arm64 zsh
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

## fedora-xfce-arm64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-02-07"]
os = "fedora"
release = "rawhide"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_arm64_2023-02-07_15-17.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "afeacadd007eb758bef489ecb91917f901e6bdaabbe219910c929f57988869b6"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.9G"
tar_bytes = 6270862336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1670506526

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230131"
previous_tag = "2023-01-31"
previous_file = "fedora-xfce_arm64_2023-01-31_15-17-rootfs.tar.zst"
previous_sha256 = "60e04cdbc863967de060e79efc58983af6504e80a021b9ca92966073e256c7f3"

current_version = "latest01"
current_date = "20230207"
old_file = "fedora-xfce_arm64_2023-01-24_14-45-rootfs.tar.zst"
old_sha256 = "3b547e7f289ab46bf95eef489a97cd254d0093ef372efc9980b9c54fe4a4e10d"
# edition 2021
# DISTRO_NAME=fedora-rawhide_arm64
# ROOTFS_FILE=fedora-xfce_arm64_2023-02-07_15-17-rootfs.tar.zst
# SHA256SUM=afeacadd007eb758bef489ecb91917f901e6bdaabbe219910c929f57988869b6
# BUILD_DATE=20230207
# BUILD_TAG=2023-02-07
# STATUS=completed
# VERSION=latest01
# END_TIME=15:17

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-07
begin = 2023-02-07 13:04:56.230201973+00:00
start-sync_0 = 14:49:44
start-zstd = 14:55:27
start-sync_1 = 15:14:56
end-sync_1 = 15:17:20
end = 2023-02-07 15:17:20.403467027+00:00

[server]
repo = "cake233/fedora-xfce-arm64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (aarch64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
