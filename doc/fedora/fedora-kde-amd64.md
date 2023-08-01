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
tag = ["kde", "2023-08-01"]
os = "fedora"
release = "rawhide"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "fedora-kde_amd64_2023-08-01_13-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0252a939533d662dd8092762ae8f67a89f7d9e83683e8afab415919bc5273808"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3118783488

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "727M"
zstd_bytes = 761925069

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230725"
previous_tag = "2023-07-25"
previous_file = "fedora-kde_amd64_2023-07-25_12-57-rootfs.tar.zst"
previous_sha256 = "bd7ff0980c35ab209c7516b66bf2891c57cd0a58570fb9685c709b0312d55f7f"

current_version = "latest02"
current_date = "20230801"
old_file = "fedora-kde_amd64_2023-07-18_12-54-rootfs.tar.zst"
old_sha256 = "15d530e836768430947324f43f381b24c2c78b52b5838fed6474326eba082789"
# edition 2021
# DISTRO_NAME=fedora-rawhide_amd64
# ROOTFS_FILE=fedora-kde_amd64_2023-08-01_13-00-rootfs.tar.zst
# SHA256SUM=0252a939533d662dd8092762ae8f67a89f7d9e83683e8afab415919bc5273808
# BUILD_DATE=20230801
# BUILD_TAG=2023-08-01
# STATUS=completed
# VERSION=latest02
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-01
begin = 2023-08-01 12:41:37.955014168+00:00
start-sync_0 = 12:45:15
start-zstd = 12:47:12
start-sync_1 = 12:59:03
end-sync_1 = 13:00:07
end = 2023-08-01 13:00:07.533438607+00:00

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
ldd = 'ldd (GNU libc) 2.37.9000'
zsh = 'zsh 5.9 (x86_64-redhat-linux-gnu)'

[port]
tcp = [5902, 36080]
```
