# ubuntu-lxqt-arm64

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
    --name ubuntu-lxqt-arm64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-arm64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-arm64 zsh
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

## ubuntu-lxqt-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-04-11", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_arm64_2023-04-11_00-54.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "92cb2b6441695634cb9379c0433d2c867169ff910a535b2a24ac991ba7d8539a"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.0G"
tar_bytes = 4221516288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1144915399

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230404"
previous_tag = "2023-04-04"
previous_file = "ubuntu-lxqt_arm64_2023-04-04_00-55-rootfs.tar.zst"
previous_sha256 = "cb44658c0c22fbba6546371002884376942c361fe49dcc49ef5e6be5de35c8e0"

current_version = "latest01"
current_date = "20230411"
old_file = "ubuntu-lxqt_arm64_2023-03-28_01-12-rootfs.tar.zst"
old_sha256 = "2ccbe62c3167a19e5474e8b517038764d0f18feefd55c753ee5cec8669693249"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-lxqt_arm64_2023-04-11_00-54-rootfs.tar.zst
# SHA256SUM=92cb2b6441695634cb9379c0433d2c867169ff910a535b2a24ac991ba7d8539a
# BUILD_DATE=20230411
# BUILD_TAG=2023-04-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:54

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-11
begin = 2023-04-11 00:02:55.388015724+00:00
start-sync_0 = 00:35:36
start-zstd = 00:38:50
start-sync_1 = 00:53:43
end-sync_1 = 00:54:49
end = 2023-04-11 00:54:49.783098096+00:00

[server]
repo = "cake233/ubuntu-lxqt-arm64"

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (aarch64-unknown-linux-gnu)'

[port]
tcp = [5902, 36080]
```
