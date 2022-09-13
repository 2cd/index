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
tag = ["mate", "2022-09-13"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-mate_amd64_2022-09-13_13-20.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f509621c831915371592a0f77b7696fbac4cfb2f1cdf849b4ccb12f1ed4d020b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5168029696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1621280946

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220906"
previous_tag = "2022-09-06"
previous_file = "fedora-mate_amd64_2022-09-06_13-39-rootfs.tar.zst"
previous_sha256 = "07318a123bda475700ac6ab6225f584b89e75c823863df771d03f36850bc401e"

current_version = "latest02"
current_date = "20220913"
old_file = "fedora-mate_amd64_2022-08-30_13-27-rootfs.tar.zst"
old_sha256 = "f2d2ac3683b069ff81392029bbc0aec8a581e595342866d69154452d82ef0008"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-mate_amd64_2022-09-13_13-20-rootfs.tar.zst
# SHA256SUM=f509621c831915371592a0f77b7696fbac4cfb2f1cdf849b4ccb12f1ed4d020b
# BUILD_DATE=20220913
# BUILD_TAG=2022-09-13
# STATUS=completed
# VERSION=latest02
# END_TIME=13:20

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-13
begin = 2022-09-13 12:48:25.364253458+00:00
start-sync_0 = 12:54:53
start-zstd = 12:59:24
start-sync_1 = 13:19:00
end-sync_1 = 13:20:32
end = 2022-09-13 13:20:32.244782838+00:00

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
ldd = 'ldd (GNU libc) 2.36.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
