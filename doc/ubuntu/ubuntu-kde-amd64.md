# ubuntu-kde-amd64

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
    --name ubuntu-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-kde-amd64 zsh
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

## ubuntu-kde-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kde", "2023-11-21", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2023-11-21_00-48.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2b3050bfe0b03340514765b902de82209f8ae1b8555bb8dbeaa1ba4296b9ec31"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.7G"
tar_bytes = 5042964992

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1428268568

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231114"
previous_tag = "2023-11-14"
previous_file = "ubuntu-kde_amd64_2023-11-14_01-03-rootfs.tar.zst"
previous_sha256 = "cac3d82f5065e865f9c742c263c3d1c75a0912b431e49f3fc338221c2217bf89"

current_version = "latest02"
current_date = "20231121"
old_file = "ubuntu-kde_amd64_2023-11-07_00-49-rootfs.tar.zst"
old_sha256 = "a485320675e539727fb381603f467cc1e06b99e45c1f6878583b9e50adaf7d9f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2023-11-21_00-48-rootfs.tar.zst
# SHA256SUM=2b3050bfe0b03340514765b902de82209f8ae1b8555bb8dbeaa1ba4296b9ec31
# BUILD_DATE=20231121
# BUILD_TAG=2023-11-21
# STATUS=completed
# VERSION=latest02
# END_TIME=00:48

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-21
begin = 2023-11-21 00:23:54.079014581+00:00
start-sync_0 = 00:30:03
start-zstd = 00:33:00
start-sync_1 = 00:47:24
end-sync_1 = 00:48:28
end = 2023-11-21 00:48:28.756816471+00:00

[server]
repo = "cake233/ubuntu-kde-amd64"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
