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
tag = ["kde", "2023-01-24", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2023-01-24_00-42.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a0f41e5770c60eff8ba0691e9251eb4764420f42f44c4642fe035308e10192ce"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.5G"
tar_bytes = 4787328512

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.3G"
zstd_bytes = 1323266902

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230117"
previous_tag = "2023-01-17"
previous_file = "ubuntu-kde_amd64_2023-01-17_00-35-rootfs.tar.zst"
previous_sha256 = "fa035dcd560fb7dbf7db86b5cf78f65e44e1ba3ac178d43c546f6aea8b300569"

current_version = "latest02"
current_date = "20230124"
old_file = "ubuntu-kde_amd64_2023-01-10_00-32-rootfs.tar.zst"
old_sha256 = "e858f1f7f05ad1367b53c25f83aadb75f8a7e2f4a443d653886464c5b57b92f5"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2023-01-24_00-42-rootfs.tar.zst
# SHA256SUM=a0f41e5770c60eff8ba0691e9251eb4764420f42f44c4642fe035308e10192ce
# BUILD_DATE=20230124
# BUILD_TAG=2023-01-24
# STATUS=completed
# VERSION=latest02
# END_TIME=00:42

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-24
begin = 2023-01-24 00:03:06.419849540+00:00
start-sync_0 = 00:13:30
start-zstd = 00:19:24
start-sync_1 = 00:40:30
end-sync_1 = 00:42:06
end = 2023-01-24 00:42:06.428968114+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.36-0ubuntu4) 2.36'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
