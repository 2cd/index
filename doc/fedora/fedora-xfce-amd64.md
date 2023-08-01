# fedora-xfce-amd64

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
    --name fedora-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-xfce-amd64 zsh
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

## fedora-xfce-amd64.toml

```toml
[main]
name = "fedora"
tag = ["xfce", "2023-08-01"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-xfce_amd64_2023-08-01_12-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "80c98d95da4153f2107b8a998cfeaa637b0289f20a6662ce5198808f85ad2fdf"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3212070400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "771M"
zstd_bytes = 807715137

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230725"
previous_tag = "2023-07-25"
previous_file = "fedora-xfce_amd64_2023-07-25_12-54-rootfs.tar.zst"
previous_sha256 = "a61e798cc043772122448c7a302204395e9dc4e021ec4ab324bc6e46e7c9de8d"

current_version = "latest02"
current_date = "20230801"
old_file = "fedora-xfce_amd64_2023-07-18_12-54-rootfs.tar.zst"
old_sha256 = "18a0f6c129f4ebb28615f9a5e962768d6660eaeb56bd594016c593b28126cdb4"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-xfce_amd64_2023-08-01_12-58-rootfs.tar.zst
# SHA256SUM=80c98d95da4153f2107b8a998cfeaa637b0289f20a6662ce5198808f85ad2fdf
# BUILD_DATE=20230801
# BUILD_TAG=2023-08-01
# STATUS=completed
# VERSION=latest02
# END_TIME=12:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-01
begin = 2023-08-01 12:41:39.410250837+00:00
start-sync_0 = 12:44:40
start-zstd = 12:46:41
start-sync_1 = 12:57:37
end-sync_1 = 12:58:54
end = 2023-08-01 12:58:54.720013039+00:00

[server]
repo = "cake233/fedora-xfce-amd64"

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
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
