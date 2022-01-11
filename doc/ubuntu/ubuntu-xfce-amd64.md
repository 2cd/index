# ubuntu-xfce-amd64

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
    --name ubuntu-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/ubuntu-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it ubuntu-xfce-amd64 zsh
```

The default user is root.

After entering the container, you can create a new user, and then switch to it.

Finally, run the following commands.

```sh
    startvnc
```

or

```sh
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

## ubuntu-xfce-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["xfce", "2022-01-11", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "ubuntu-xfce_amd64_2022-01-11_00-39.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "eb62ce0d4f18c827ede6ffc9dc198e7862830866f19086072a7b211c704d56b9"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.8G"
tar_bytes = 2967175168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "766M"
zstd_bytes = 803033056

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220104"
previous_tag = "2022-01-04"
previous_file = "ubuntu-xfce_amd64_2022-01-04_00-38-rootfs.tar.zst"
previous_sha256 = "6bb75267d4319568196c72df20cc8cb0f5b29ba902bbfc3549431ccaaefb70f0"

current_version = "latest01"
current_date = "20220111"
old_file = "ubuntu-xfce_amd64_2021-12-28_00-39-rootfs.tar.zst"
old_sha256 = "4def86cecf373ff2d886a45b78713e0a57d595d4917a913c7b0791ef53c66a74"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-xfce_amd64_2022-01-11_00-39-rootfs.tar.zst
# SHA256SUM=eb62ce0d4f18c827ede6ffc9dc198e7862830866f19086072a7b211c704d56b9
# BUILD_DATE=20220111
# BUILD_TAG=2022-01-11
# STATUS=completed
# VERSION=latest01
# END_TIME=00:39

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-11
begin = 2022-01-11 00:23:05.827184738+00:00
start-sync_0 = 00:28:28
start-zstd = 00:30:48
start-sync_1 = 00:38:30
end-sync_1 = 00:39:20
end = 2022-01-11 00:39:20.183299749+00:00

[server]
repo = "cake233/ubuntu-xfce-amd64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'ldd (Ubuntu GLIBC 2.34-0ubuntu3) 2.34'
zsh = 'zsh 5.8 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
