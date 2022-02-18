# manjaro-xfce-amd64

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
    --name manjaro-xfce-amd64 \
    -e LANG=en_US.UTF-8 \
    cake233/manjaro-xfce-amd64

# optional: bind audio server
# host cmd: pactl load-module module-native-protocol-unix socket=/path/to/src.socket
# docker args: -v /path/to/src.socket:/path/to/target.socket \
# -e PULSE_SERVER=unix:/path/to/target.socket

```

## How to start vnc?

```sh
    docker exex -it manjaro-xfce-amd64 zsh
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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2022-02-18"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = true

[file]
name = "manjaro-xfce_amd64_2022-02-18_12-51.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "51b09f9169bffeec440626e6c91f24424ef60e6565ac85f041d4dbbd70b22622"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.7G"
tar_bytes = 3889072640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1162467870

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220211"
previous_tag = "2022-02-11"
previous_file = "manjaro-xfce_amd64_2022-02-11_12-42-rootfs.tar.zst"
previous_sha256 = "c0c27dd51e5335cdc3681a3c8c36a9f2ef2357bcc26fbb73c7828dff82344f45"

current_version = "latest01"
current_date = "20220218"
old_file = "manjaro-xfce_amd64_2022-02-04_12-57-rootfs.tar.zst"
old_sha256 = "df1c3a23ca4df7e5a317815cb79cee029966824fac6e0e28a950e0e3069efe27"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2022-02-18_12-51-rootfs.tar.zst
# SHA256SUM=51b09f9169bffeec440626e6c91f24424ef60e6565ac85f041d4dbbd70b22622
# BUILD_DATE=20220218
# BUILD_TAG=2022-02-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:51

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-18
begin = 2022-02-18 12:22:20.354484834+00:00
start-sync_0 = 12:30:36
start-zstd = 12:34:36
start-sync_1 = 12:50:10
end-sync_1 = 12:51:37
end = 2022-02-18 12:51:37.152959122+00:00

[server]
repo = "cake233/manjaro-xfce-amd64"

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
ldd = 'ldd (GNU libc) 2.33'
zsh = 'zsh 5.8 (x86_64-pc-linux-gnu)'

[port]
tcp = [5902, 36080]
```
