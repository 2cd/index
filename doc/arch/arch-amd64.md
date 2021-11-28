# arch-amd64

## How to run it?

```shell
docker run \
    -it \
    --name arch-amd64 \
    cake233/arch-amd64
```

## How to exec shell?

```shell
    docker exec -it arch-amd64 sh
```

## arch-amd64.toml

```toml
[main]
name = "arch"
tag = ["base", "2021-11-28"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "arch_amd64_2021-11-28_22-59.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "9a6fdae27945ca2b95a06cf7176a32e2d122ac3365b427a65bb0e39cc9350abb"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "622M"
tar_bytes = 651385856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "178M"
zstd_bytes = 186626859

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=arch_amd64
# ROOTFS_FILE=arch_amd64_2021-11-28_22-59.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=22:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:57:00.225846518+00:00
start-sync_0 = 22:58:24
start-zstd = 22:59:06
start-sync_1 = 22:59:17
end-sync_1 = 22:59:34
end = 2021-11-28 22:59:34.202164108+00:00

[server]
repo = "cake233/arch-amd64"

[server.node1]
name = "cn"
current = false
last = false
split = false

[server.node2]
name = "us"
current = false
last = false
split = false
part = 12

[server.node3]
name = "global"
current = false
last = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
