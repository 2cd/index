# ubuntu-kinetic-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-kinetic-arm64 \
    cake233/ubuntu-kinetic-arm64
```

## How to exec shell?

```sh
docker exec -it ubuntu-kinetic-arm64 sh
```

## ubuntu-kinetic-arm64.toml

```toml
[main]
name = "ubuntu"
tag = ["kinetic", "2022-05-12", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_arm64_2022-05-12_00-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "afe82e634d02885b351fd3b0bfca0de7096e5075b947bfbd8363352d49329de2"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "410M"
tar_bytes = 429003264

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "69M"
zstd_bytes = 71663632

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220511"
previous_tag = "2022-05-11"
previous_file = "ubuntu-kinetic_arm64_2022-05-11_00-10-rootfs.tar.zst"
previous_sha256 = "6a4cb536b919b2dea51c979fd0387321c2d8a5ba07a5d910fdb18e5f650788b2"

current_version = "latest01"
current_date = "20220512"
old_file = "ubuntu-kinetic_arm64_2022-05-10_00-11-rootfs.tar.zst"
old_sha256 = "aa591c3f03eb25119e8dc574b66b9ae6201bc4f3d0bc398b3b9f04f7c104875f"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kinetic_arm64_2022-05-12_00-11-rootfs.tar.zst
# SHA256SUM=afe82e634d02885b351fd3b0bfca0de7096e5075b947bfbd8363352d49329de2
# BUILD_DATE=20220512
# BUILD_TAG=2022-05-12
# STATUS=completed
# VERSION=latest01
# END_TIME=00:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-12
begin = 2022-05-12 00:04:19.092093135+00:00
start-sync_0 = 00:09:45
start-zstd = 00:10:14
start-sync_1 = 00:11:43
end-sync_1 = 00:11:53
end = 2022-05-12 00:11:53.411857814+00:00

[server]
repo = "cake233/ubuntu-kinetic-arm64"

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
