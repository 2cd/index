# debian-xfce-amd64

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
    --name debian-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-xfce-amd64 zsh
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

## debian-xfce-amd64.toml

```toml
[main]
name = "debian"
tag = ["xfce", "2022-05-18"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-xfce_amd64_2022-05-18_12-45.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "06435a9c4c7be27d9de1ddec0997c4bf09b4cb059ab1ce06a659b8b5661a8da4"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3957511680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1120980391

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220511"
previous_tag = "2022-05-11"
previous_file = "debian-xfce_amd64_2022-05-11_12-42-rootfs.tar.zst"
previous_sha256 = "0de32a7a63cc61945f2e8d45d3a717a659dc1b35286fdd5b882f89cffb8706fe"

current_version = "latest02"
current_date = "20220518"
old_file = "debian-xfce_amd64_2022-05-04_14-45-rootfs.tar.zst"
old_sha256 = "04be40af012d61bbd9a5927f0370ea3df793354b13eccfda82143f083c33ad2c"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-xfce_amd64_2022-05-18_12-45-rootfs.tar.zst
# SHA256SUM=06435a9c4c7be27d9de1ddec0997c4bf09b4cb059ab1ce06a659b8b5661a8da4
# BUILD_DATE=20220518
# BUILD_TAG=2022-05-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:45

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-18
begin = 2022-05-18 12:18:13.135368311+00:00
start-sync_0 = 12:25:04
start-zstd = 12:29:07
start-sync_1 = 12:44:12
end-sync_1 = 12:45:31
end = 2022-05-18 12:45:31.826750811+00:00

[server]
repo = "cake233/debian-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
