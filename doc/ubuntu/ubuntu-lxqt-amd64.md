# ubuntu-lxqt-amd64

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
    --name ubuntu-lxqt-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-lxqt-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-lxqt-amd64 zsh
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

## ubuntu-lxqt-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["lxqt", "2023-01-17", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-lxqt_amd64_2023-01-17_00-28.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0daba6bac11cc01825f89bc523f495d621e8499cde7873ee2da494eb67caf716"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 4008529408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1082471066

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230110"
previous_tag = "2023-01-10"
previous_file = "ubuntu-lxqt_amd64_2023-01-10_00-34-rootfs.tar.zst"
previous_sha256 = "121b64c1c312d99a95215c382e8235395a645091c33b019294092a0908856522"

current_version = "latest01"
current_date = "20230117"
old_file = "ubuntu-lxqt_amd64_2023-01-03_00-27-rootfs.tar.zst"
old_sha256 = "4b677fa3dad2967b01ea4b750013d4bd7cd32bb0b69c72982e66493d6472b9a0"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-lxqt_amd64_2023-01-17_00-28-rootfs.tar.zst
# SHA256SUM=0daba6bac11cc01825f89bc523f495d621e8499cde7873ee2da494eb67caf716
# BUILD_DATE=20230117
# BUILD_TAG=2023-01-17
# STATUS=completed
# VERSION=latest01
# END_TIME=00:28

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-17
begin = 2023-01-17 00:03:00.709268631+00:00
start-sync_0 = 00:10:00
start-zstd = 00:13:19
start-sync_1 = 00:26:51
end-sync_1 = 00:28:17
end = 2023-01-17 00:28:17.678187870+00:00

[server]
repo = "cake233/ubuntu-lxqt-amd64"

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
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
