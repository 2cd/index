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
tag = ["kde", "2022-07-19", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kde_amd64_2022-07-19_01-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "25bdac6854660f7d989f6d30ae5f0d45af84accf26cbbdcf78957f246d25d75b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.4G"
tar_bytes = 4632082944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1263988947

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220712"
previous_tag = "2022-07-12"
previous_file = "ubuntu-kde_amd64_2022-07-12_00-53-rootfs.tar.zst"
previous_sha256 = "84f14dc548f4f941017f526a48c44ae063231350f0e87b4085386e6dd74743a6"

current_version = "latest02"
current_date = "20220719"
old_file = "ubuntu-kde_amd64_2022-07-05_00-44-rootfs.tar.zst"
old_sha256 = "6b09dbb874087c5209eaa10edbd37776403040f0d9eadefacebf0f2df09f3b17"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kde_amd64_2022-07-19_01-07-rootfs.tar.zst
# SHA256SUM=25bdac6854660f7d989f6d30ae5f0d45af84accf26cbbdcf78957f246d25d75b
# BUILD_DATE=20220719
# BUILD_TAG=2022-07-19
# STATUS=completed
# VERSION=latest02
# END_TIME=01:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-19
begin = 2022-07-19 00:19:50.119184192+00:00
start-sync_0 = 00:41:27
start-zstd = 00:46:32
start-sync_1 = 01:06:03
end-sync_1 = 01:07:36
end = 2022-07-19 01:07:36.076069676+00:00

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
ldd = 'ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35'
zsh = 'zsh 5.9 (x86_64-ubuntu-linux-gnu)'

[port]
tcp = [5902, 36080]
```
