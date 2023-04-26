# arch-kde-amd64

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
    --name arch-kde-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-kde-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-kde-amd64 zsh
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

## arch-kde-amd64.toml

```toml
[main]
name = "arch"
tag = ["kde", "2023-04-26"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-kde_amd64_2023-04-26_01-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "844f127b7ddcb1871eba813b2f00010eabc5a61724612a680a3a085620603ca8"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "4.6G"
tar_bytes = 4839566336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.4G"
zstd_bytes = 1451568942

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230419"
previous_tag = "2023-04-19"
previous_file = "arch-kde_amd64_2023-04-19_00-58-rootfs.tar.zst"
previous_sha256 = "136b36df2fa30b4b460295d654ffc1ca0bf6183639f8ceaa6c9563c71eb58c40"

current_version = "latest01"
current_date = "20230426"
old_file = "arch-kde_amd64_2023-04-12_01-05-rootfs.tar.zst"
old_sha256 = "1a5b1c5e7036e3e200860c9331c26c6d3c268bcd5e828afe76be01e9d2669613"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-kde_amd64_2023-04-26_01-09-rootfs.tar.zst
# SHA256SUM=844f127b7ddcb1871eba813b2f00010eabc5a61724612a680a3a085620603ca8
# BUILD_DATE=20230426
# BUILD_TAG=2023-04-26
# STATUS=completed
# VERSION=latest01
# END_TIME=01:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-26
begin = 2023-04-26 00:34:48.991606526+00:00
start-sync_0 = 00:41:01
start-zstd = 00:47:41
start-sync_1 = 01:08:02
end-sync_1 = 01:09:35
end = 2023-04-26 01:09:35.906950675+00:00

[server]
repo = "cake233/arch-kde-amd64"

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
ldd = 'ldd (GNU libc) 2.37'
zsh = 'zsh 5.9 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
