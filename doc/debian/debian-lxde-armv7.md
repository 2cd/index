# debian-lxde-armv7

## How to run it?

```sh
# install docker
if [ -z "$(command -v docker)" ]; then
    apt update
    apt install docker.io
    # If your host architecture is not armv7, then install qemu & binfmt-support.
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
    --name debian-lxde-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/debian-lxde-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it debian-lxde-armv7 zsh
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

## debian-lxde-armv7.toml

```toml
[main]
name = "debian"
tag = ["lxde", "2024-01-17"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2024-01-17_13-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ec33c6a382f2268dc42838fcfc68bac58e3c25284622bf2342bc050cd52b0828"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3190358528

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "961M"
zstd_bytes = 1007132731

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231122"
previous_tag = "2023-11-22"
previous_file = "debian-lxde_armhf_2023-11-22_13-00-rootfs.tar.zst"
previous_sha256 = "5e859bc618e740900357c4753d2799d35a90253eee9defcc2868ef3b36135800"

current_version = "latest01"
current_date = "20240117"
old_file = "debian-lxde_armhf_2023-11-15_13-15-rootfs.tar.zst"
old_sha256 = "166f1e146f8fe6c310be83c182007b8a45a3c84f49fdfe6cf9518c1dece9faeb"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2024-01-17_13-00-rootfs.tar.zst
# SHA256SUM=ec33c6a382f2268dc42838fcfc68bac58e3c25284622bf2342bc050cd52b0828
# BUILD_DATE=20240117
# BUILD_TAG=2024-01-17
# STATUS=completed
# VERSION=latest01
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-17
begin = 2024-01-17 12:32:28.948718698+00:00
start-sync_0 = 12:51:14
start-zstd = 12:52:47
start-sync_1 = 12:59:55
end-sync_1 = 13:00:40
end = 2024-01-17 13:00:40.057963039+00:00

[server]
repo = "cake233/debian-lxde-armv7"

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
