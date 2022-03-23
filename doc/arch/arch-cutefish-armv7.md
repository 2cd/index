# arch-cutefish-armv7

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
    --name arch-cutefish-armv7 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-cutefish-armv7

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-cutefish-armv7 zsh
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

## arch-cutefish-armv7.toml

```toml
[main]
name = "arch"
tag = ["cutefish", "2022-03-23"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = true

[file]
name = "arch-cutefish_armhf_2022-03-23_00-53.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e149f5d2fdd549d690685906733db6951257b7210f32febff80ac876fd9f40d9"

# zstd: [1-22]
zstd-level = 15

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.3G"
tar_bytes = 3456921600

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.2G"
zstd_bytes = 1186723074

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "arch-cutefish_armhf_2022-03-16_00-56-rootfs.tar.zst"
previous_sha256 = "c9631e5619277c0a8b296927933671c6bb51c4cfe729d0881c6d828ae064720f"

current_version = "latest02"
current_date = "20220323"
old_file = "arch-cutefish_armhf_2022-03-09_01-02-rootfs.tar.zst"
old_sha256 = "627d55ca245a65dd2d6ce89297ccc9e56fc66524eb12a4c97d9411186aac6101"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-cutefish_armhf_2022-03-23_00-53-rootfs.tar.zst
# SHA256SUM=e149f5d2fdd549d690685906733db6951257b7210f32febff80ac876fd9f40d9
# BUILD_DATE=20220323
# BUILD_TAG=2022-03-23
# STATUS=completed
# VERSION=latest02
# END_TIME=00:53

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-23
begin = 2022-03-23 00:33:25.545600099+00:00
start-sync_0 = 00:45:43
start-zstd = 00:48:47
start-sync_1 = 00:52:42
end-sync_1 = 00:53:55
end = 2022-03-23 00:53:55.182699521+00:00

[server]
repo = "cake233/arch-cutefish-armv7"

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.8.1 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
