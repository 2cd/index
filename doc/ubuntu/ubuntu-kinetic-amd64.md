# ubuntu-kinetic-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-kinetic-amd64 \
    cake233/ubuntu-kinetic-amd64
```

## How to exec shell?

```sh
docker exec -it ubuntu-kinetic-amd64 sh
```

## ubuntu-kinetic-amd64.toml

```toml
[main]
name = "ubuntu"
tag = ["kinetic", "2022-05-12", "devel"]
os = "ubuntu"
release = "dev"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_amd64_2022-05-12_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9b8220bd548744b34be5445212b0bc08b766fd99d62a71d93e4ea301d47426c7"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "420M"
tar_bytes = 439493120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "71M"
zstd_bytes = 73452404

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220511"
previous_tag = "2022-05-11"
previous_file = "ubuntu-kinetic_amd64_2022-05-11_00-07-rootfs.tar.zst"
previous_sha256 = "0c3b396208c454e4904849685f63b9bf9b871c3f39e116f6a62d300357636f11"

current_version = "latest01"
current_date = "20220512"
old_file = "ubuntu-kinetic_amd64_2022-05-10_00-07-rootfs.tar.zst"
old_sha256 = "bcd43675374eb7893c68063e042a1247196438100fbf459e0055da674375b270"
# edition 2021
# DISTRO_NAME=ubuntu-dev_amd64
# ROOTFS_FILE=ubuntu-kinetic_amd64_2022-05-12_00-07-rootfs.tar.zst
# SHA256SUM=9b8220bd548744b34be5445212b0bc08b766fd99d62a71d93e4ea301d47426c7
# BUILD_DATE=20220512
# BUILD_TAG=2022-05-12
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-12
begin = 2022-05-12 00:04:22.105896901+00:00
start-sync_0 = 00:05:17
start-zstd = 00:05:49
start-sync_1 = 00:07:28
end-sync_1 = 00:07:41
end = 2022-05-12 00:07:41.425255031+00:00

[server]
repo = "cake233/ubuntu-kinetic-amd64"

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
```
