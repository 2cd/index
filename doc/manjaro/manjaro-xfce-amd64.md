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

## manjaro-xfce-amd64.toml

```toml
[main]
name = "manjaro"
tag = ["xfce", "2023-02-24"]
os = "manjaro"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = true
syntax_version = "0.0.0-alpha.4"

[file]
name = "manjaro-xfce_amd64_2023-02-24_12-50.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "42e9884ccef6db9e5e7461b57ea5663ba20ca285fbc830151849021f983ca11e"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "3.8G"
tar_bytes = 3977127424

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "1.1G"
zstd_bytes = 1171851166

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230217"
previous_tag = "2023-02-17"
previous_file = "manjaro-xfce_amd64_2023-02-17_12-55-rootfs.tar.zst"
previous_sha256 = "324df03da855f762a18b5a061cf6902da68d58ceec6399dbd6a47d3f1c3b54ae"

current_version = "latest02"
current_date = "20230224"
old_file = "manjaro-xfce_amd64_2023-02-10_12-43-rootfs.tar.zst"
old_sha256 = "b4be2b9cc93e32df01aa8a3a536ddb46c58dd855c59db5dc170a5f1536fbf8e9"
# edition 2021
# DISTRO_NAME=manjaro-stable_amd64
# ROOTFS_FILE=manjaro-xfce_amd64_2023-02-24_12-50-rootfs.tar.zst
# SHA256SUM=42e9884ccef6db9e5e7461b57ea5663ba20ca285fbc830151849021f983ca11e
# BUILD_DATE=20230224
# BUILD_TAG=2023-02-24
# STATUS=completed
# VERSION=latest02
# END_TIME=12:50

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-24
begin = 2023-02-24 12:20:27.124949728+00:00
start-sync_0 = 12:25:41
start-zstd = 12:29:33
start-sync_1 = 12:49:00
end-sync_1 = 12:50:26
end = 2023-02-24 12:50:26.558725946+00:00

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
