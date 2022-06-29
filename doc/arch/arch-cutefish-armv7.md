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
tag = ["cutefish", "2022-06-29"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch-cutefish_armhf_2022-06-29_01-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "605fbd6b2e034375c1ea97ed63cf7040cd486f1f502b65f00ecbb6f3b3c1238d"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.5G"
tar_bytes = 3729568768

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1160893374

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220622"
previous_tag = "2022-06-22"
previous_file = "arch-cutefish_armhf_2022-06-22_00-58-rootfs.tar.zst"
previous_sha256 = "fbb72845189576f85bc0f562e5efbce195fad987ecd471aed53d73b471fe990c"

current_version = "latest02"
current_date = "20220629"
old_file = "arch-cutefish_armhf_2022-06-15_01-04-rootfs.tar.zst"
old_sha256 = "755b58f36393370d6acfc289a2ee49bbe0ece2192b03731c4508731bb494564f"
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-cutefish_armhf_2022-06-29_01-03-rootfs.tar.zst
# SHA256SUM=605fbd6b2e034375c1ea97ed63cf7040cd486f1f502b65f00ecbb6f3b3c1238d
# BUILD_DATE=20220629
# BUILD_TAG=2022-06-29
# STATUS=completed
# VERSION=latest02
# END_TIME=01:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-29
begin = 2022-06-29 00:32:00.198038948+00:00
start-sync_0 = 00:45:52
start-zstd = 00:49:02
start-sync_1 = 01:02:19
end-sync_1 = 01:03:30
end = 2022-06-29 01:03:30.412575698+00:00

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
ldd = 'ldd (GNU libc) 2.35'
zsh = 'zsh 5.9 (armv7l-unknown-linux-gnueabihf)'

[port]
tcp = [5902, 36080]
```
