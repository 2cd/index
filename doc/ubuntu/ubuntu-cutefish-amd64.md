# ubuntu-cutefish-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-cutefish-amd64 \
    cake233/ubuntu-cutefish-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-cutefish-amd64 sh
```

## ubuntu-cutefish-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["cutefish", "2022-03-03", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ubuntu-cutefish_amd64_2022-03-03_02-26.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "aeb4ae322be1bfd71d99bbd537c1f5f50a962cec1f3c501f29db1719b2ec1156"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "168M"
tar_bytes = 175367168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "114M"
zstd_bytes = 118649293

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220303"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-cutefish_amd64_2022-03-03_02-26-rootfs.tar.zst
# SHA256SUM=aeb4ae322be1bfd71d99bbd537c1f5f50a962cec1f3c501f29db1719b2ec1156
# BUILD_DATE=20220303
# BUILD_TAG=2022-03-03
# STATUS=completed
# VERSION=latest01
# END_TIME=02:26

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-03
begin = 2022-03-03 01:56:31.683901872+00:00
start-sync_0 = 02:25:05
start-zstd = 02:26:06
start-sync_1 = 02:26:11
end-sync_1 = 02:26:24
end = 2022-03-03 02:26:24.512068699+00:00

[server]
repo = "cake233/ubuntu-cutefish-amd64"

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
```
