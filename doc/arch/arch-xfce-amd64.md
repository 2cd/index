# arch-xfce-amd64

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
    --name arch-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/arch-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it arch-xfce-amd64 zsh
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

## arch-xfce-amd64.toml

```toml
[main]
name = "arch"
tag = ["xfce", "2022-04-20"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true
syntax_version = "0.0.0-alpha.3"

[file]
name = "arch-xfce_amd64_2022-04-20_00-47.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5a64b5181c141407d4d01ea06ed8d18065cbcf9ba80e07cd063cf8a20b0fd84b"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.6G"
tar_bytes = 3839581184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1141721948

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220413"
previous_tag = "2022-04-13"
previous_file = "arch-xfce_amd64_2022-04-13_00-58-rootfs.tar.zst"
previous_sha256 = "a46471b2e2b8d8daec0a15c0e5feaf2d304208ad386ba1d5de41ba1189823ded"

current_version = "latest02"
current_date = "20220420"
old_file = "arch-xfce_amd64_2022-03-29_23-58-rootfs.tar.zst"
old_sha256 = "f7cf2e67f9e7cf767a81394eb1c500c6571b8de008175516574a4883845f0e44"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch-xfce_amd64_2022-04-20_00-47-rootfs.tar.zst
# SHA256SUM=5a64b5181c141407d4d01ea06ed8d18065cbcf9ba80e07cd063cf8a20b0fd84b
# BUILD_DATE=20220420
# BUILD_TAG=2022-04-20
# STATUS=completed
# VERSION=latest02
# END_TIME=00:47

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-20
begin = 2022-04-20 00:25:50.132167291+00:00
start-sync_0 = 00:30:02
start-zstd = 00:33:11
start-sync_1 = 00:46:50
end-sync_1 = 00:47:57
end = 2022-04-20 00:47:57.177141868+00:00

[server]
repo = "cake233/arch-xfce-amd64"

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
zsh = 'zsh 5.8.1 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
