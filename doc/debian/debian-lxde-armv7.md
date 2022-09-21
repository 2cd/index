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
tag = ["lxde", "2022-09-21"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-lxde_armhf_2022-09-21_13-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9ef5b4c83b3744eb490f213e3f127b44da6e428ffc658313fcfc1a754495ec7c"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.0G"
tar_bytes = 3115462656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "932M"
zstd_bytes = 976330730

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220914"
previous_tag = "2022-09-14"
previous_file = "debian-lxde_armhf_2022-09-14_13-06-rootfs.tar.zst"
previous_sha256 = "20d99aaffb65be07fc2cbd1d086029b6f6a90e8ccf15e824558e26cf79b1995a"

current_version = "latest02"
current_date = "20220921"
old_file = "debian-lxde_armhf_2022-09-07_12-56-rootfs.tar.zst"
old_sha256 = "4fd014023743e87fd30ecb56cfafa70f6d4235dd27c481b4f28bf0ba51635eac"
# edition 2021
# DISTRO_NAME=debian-sid_armhf
# ROOTFS_FILE=debian-lxde_armhf_2022-09-21_13-00-rootfs.tar.zst
# SHA256SUM=9ef5b4c83b3744eb490f213e3f127b44da6e428ffc658313fcfc1a754495ec7c
# BUILD_DATE=20220921
# BUILD_TAG=2022-09-21
# STATUS=completed
# VERSION=latest02
# END_TIME=13:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-21
begin = 2022-09-21 12:17:59.281925996+00:00
start-sync_0 = 12:45:57
start-zstd = 12:48:23
start-sync_1 = 12:59:07
end-sync_1 = 13:00:21
end = 2022-09-21 13:00:21.537974295+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-8) 2.34'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
