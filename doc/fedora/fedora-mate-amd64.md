# fedora-mate-amd64

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not amd64, then install qemu & binfmt-support.
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
    --name fedora-mate-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-mate-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-mate-amd64 zsh
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

## fedora-mate-amd64.toml

```toml
[main]
name = "fedora"
tag = ["mate", "2023-03-07"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2023-03-07_13-40.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "218ea36141ea384aeecb2a747b9761e49ee46e17ca6488a48bbc8ef5a9430ec5"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "5.0G"
tar_bytes = 5286313984

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.5G"
zstd_bytes = 1597886063

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230228"
previous_tag = "2023-02-28"
previous_file = "fedora-mate_amd64_2023-02-28_13-36-rootfs.tar.zst"
previous_sha256 = "df6c86512fe9a11b4df889668c3739b4676833f23b97688119ff1c467385e40d"

current_version = "latest01"
current_date = "20230307"
old_file = "fedora-mate_amd64_2023-02-21_13-41-rootfs.tar.zst"
old_sha256 = "5e779afb903912b5338a70c8c02cedb3756c2430a14e97fd5f04f0a969c3bc99"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2023-03-07_13-40-rootfs.tar.zst
# SHA256SUM=218ea36141ea384aeecb2a747b9761e49ee46e17ca6488a48bbc8ef5a9430ec5
# BUILD_DATE=20230307
# BUILD_TAG=2023-03-07
# STATUS=completed
# VERSION=latest01
# END_TIME=13:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-07
begin = 2023-03-07 13:05:16.112027217+00:00
start-sync_0 = 13:12:55
start-zstd = 13:17:44
start-sync_1 = 13:39:13
end-sync_1 = 13:40:57
end = 2023-03-07 13:40:57.837877284+00:00

[server]
repo = "cake233/fedora-mate-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
