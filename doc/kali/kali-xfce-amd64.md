# kali-xfce-amd64

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
    --name kali-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/kali-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it kali-xfce-amd64 zsh
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

## kali-xfce-amd64.toml

```toml
[main]
name = "kali"
tag = ["xfce", "2022-09-15"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "kali-xfce_amd64_2022-09-15_13-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e4bfe9b350cca566ddb4ff4e342b6580979919b99ddc6e9cda1b7f669f257e62"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "6.0G"
tar_bytes = 6380836864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.6G"
zstd_bytes = 1710965301

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220908"
previous_tag = "2022-09-08"
previous_file = "kali-xfce_amd64_2022-09-08_13-03-rootfs.tar.zst"
previous_sha256 = "a0de3bf7b51a9a9f03df4c3f1f668ae7e3514ee8162918e250607cd8e5141b0b"

current_version = "latest01"
current_date = "20220915"
old_file = "kali-xfce_amd64_2022-09-01_12-57-rootfs.tar.zst"
old_sha256 = "aa1477368b8124e06bbf55371623a5c7b1ee52d31e05d823fc5e27db49efeca5"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-xfce_amd64_2022-09-15_13-11-rootfs.tar.zst
# SHA256SUM=e4bfe9b350cca566ddb4ff4e342b6580979919b99ddc6e9cda1b7f669f257e62
# BUILD_DATE=20220915
# BUILD_TAG=2022-09-15
# STATUS=completed
# VERSION=latest01
# END_TIME=13:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-15
begin = 2022-09-15 12:23:01.132499993+00:00
start-sync_0 = 12:35:35
start-zstd = 12:43:34
start-sync_1 = 13:09:47
end-sync_1 = 13:11:37
end = 2022-09-15 13:11:37.650395401+00:00

[server]
repo = "cake233/kali-xfce-amd64"

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'

[port]
tcp = [5902, 36080]
```
