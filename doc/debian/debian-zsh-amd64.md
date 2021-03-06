# debian-zsh-amd64

## How to run it?

```sh
docker run \
    -it \
    --name debian-zsh-amd64 \
    cake233/debian-zsh-amd64
```

## How to exec shell?

```sh
docker exec -it debian-zsh-amd64 zsh
```

## debian-zsh-amd64.toml

```toml
[main]
name = "debian"
tag = ["zsh", "2022-07-20"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "debian-zsh_amd64_2022-07-20_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "739a1203df6af79a460f79a4ddb0ebb04eeac1d988416df1764cd06c51271b25"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "756M"
tar_bytes = 792487936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "148M"
zstd_bytes = 154334998

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220713"
previous_tag = "2022-07-13"
previous_file = "debian-zsh_amd64_2022-07-13_12-08-rootfs.tar.zst"
previous_sha256 = "445fac843d9af0443960921a82c2a8850dd83d46a542fd6d6bb829a5e6b76286"

current_version = "latest01"
current_date = "20220720"
old_file = "debian-zsh_amd64_2022-07-06_12-08-rootfs.tar.zst"
old_sha256 = "1bee778f108bf4d5d21de7611970104b81d0c765198a1bc6f8fe20aeee506643"
# edition 2021
# DISTRO_NAME=debian-sid_amd64
# ROOTFS_FILE=debian-zsh_amd64_2022-07-20_12-09-rootfs.tar.zst
# SHA256SUM=739a1203df6af79a460f79a4ddb0ebb04eeac1d988416df1764cd06c51271b25
# BUILD_DATE=20220720
# BUILD_TAG=2022-07-20
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-20
begin = 2022-07-20 12:02:29.190801092+00:00
start-sync_0 = 12:04:18
start-zstd = 12:06:06
start-sync_1 = 12:08:57
end-sync_1 = 12:09:11
end = 2022-07-20 12:09:11.785757338+00:00

[server]
repo = "cake233/debian-zsh-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
zsh = 'zsh 5.9 (x86_64-debian-linux-gnu)'
```
