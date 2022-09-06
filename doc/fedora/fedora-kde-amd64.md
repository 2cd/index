# fedora-kde-amd64

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
    --name fedora-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/fedora-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it fedora-kde-amd64 zsh
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

## fedora-kde-amd64.toml

```toml
[main]
name = "fedora"
tag = ["kde", "2022-09-06"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2022-09-06_13-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2ca67aaf38266238dc03474dc26ae14f2475f2c270fb354e52f40863ebf3340c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.9G"
tar_bytes = 5212907008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1629355065

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220830"
previous_tag = "2022-08-30"
previous_file = "fedora-kde_amd64_2022-08-30_13-29-rootfs.tar.zst"
previous_sha256 = "d56c2b5ea5a17b60c47938d7f35e7308560f92c7e783835697cd38563ca7499a"

current_version = "latest01"
current_date = "20220906"
old_file = "fedora-kde_amd64_2022-08-23_13-17-rootfs.tar.zst"
old_sha256 = "680f52daddfa49258d8519cb22441f71c05c14a79b9b8dd98a4806ff303b510c"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2022-09-06_13-33-rootfs.tar.zst
# SHA256SUM=2ca67aaf38266238dc03474dc26ae14f2475f2c270fb354e52f40863ebf3340c
# BUILD_DATE=20220906
# BUILD_TAG=2022-09-06
# STATUS=completed
# VERSION=latest01
# END_TIME=13:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-06
begin = 2022-09-06 13:02:35.717150402+00:00
start-sync_0 = 13:08:41
start-zstd = 13:13:00
start-sync_1 = 13:32:06
end-sync_1 = 13:33:38
end = 2022-09-06 13:33:38.045082841+00:00

[server]
repo = "cake233/fedora-kde-amd64"

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
