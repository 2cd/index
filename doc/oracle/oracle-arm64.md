# oracle-arm64

## How to run it?

```sh
docker run \
    -it \
    --name oracle-arm64 \
    cake233/oracle-arm64
```

## How to exec shell?

```sh
docker exec -it oracle-arm64 sh
```

## oracle-arm64.toml

```toml
[main]
name = "oracle"
tag = ["base", "2022-04-22"]
os = "oracle"
release = "base"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "oracle_arm64_2022-04-22_04-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f090ce959db9479d23cb72108ebfee96fb2249e264a0ed5bdd9a1ef75a185ccf"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "490M"
tar_bytes = 513591808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "73M"
zstd_bytes = 76030082

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220422"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=oracle_arm64
# ROOTFS_FILE=oracle_arm64_2022-04-22_04-16-rootfs.tar.zst
# SHA256SUM=f090ce959db9479d23cb72108ebfee96fb2249e264a0ed5bdd9a1ef75a185ccf
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest01
# END_TIME=04:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 04:11:19.709796668+00:00
start-sync_0 = 04:14:34
start-zstd = 04:15:04
start-sync_1 = 04:16:23
end-sync_1 = 04:16:34
end = 2022-04-22 04:16:34.654011234+00:00

[server]
repo = "cake233/oracle-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = false
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
```
