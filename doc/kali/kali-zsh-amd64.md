# kali-zsh-amd64

## How to run it?

```shell
docker run \
    -it \
    --name kali-zsh-amd64 \
    cake233/kali-zsh-amd64
```

## How to exec shell?

```shell
    docker exec -it kali-zsh-amd64 zsh
```

## kali-zsh-amd64.toml

```toml
[main]
name = "kali"
tag = ["zsh", "2021-12-02"]
os = "kali"
release = "rolling"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "kali-zsh_amd64_2021-12-02_12-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "ae747dbaea8db8d84032857fd396a6ea697220c081e6d7031305fb67fb783ba6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "729M"
tar_bytes = 764280832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "141M"
zstd_bytes = 146859552

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211130"
last_tag = "2021-11-30"
last_file = "kali-zsh_amd64_2021-11-30_15-02-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211202"
old_file = "kali-zsh-amd64_2021-11-28_21-00-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=kali-rolling_amd64
# ROOTFS_FILE=kali-zsh_amd64_2021-12-02_12-08-rootfs.tar.zst
# BUILD_DATE=20211202
# BUILD_TAG=2021-12-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-02
begin = 2021-12-02 12:01:51.865310504+00:00
start-sync_0 = 12:03:57
start-zstd = 12:05:44
start-sync_1 = 12:08:05
end-sync_1 = 12:08:20
end = 2021-12-02 12:08:20.926061262+00:00

[server]
repo = "cake233/kali-zsh-amd64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
