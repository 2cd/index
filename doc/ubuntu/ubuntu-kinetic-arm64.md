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
tag = ["kinetic", "2022-05-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_arm64_2022-05-07_00-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4780171df8810ebc66a3bd8c003c39d19894deace3fe8283f56a275eb16386eb"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "410M"
tar_bytes = 428989440

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "69M"
zstd_bytes = 71561590

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220506"
previous_tag = "2022-05-06"
previous_file = "ubuntu-kinetic_arm64_2022-05-06_00-10-rootfs.tar.zst"
previous_sha256 = "bf188181205c549062e44fd83cb2db00a2177c22d4d03f4ee0a16c95b18d16f8"

current_version = "latest01"
current_date = "20220507"
old_file = "ubuntu-kinetic_arm64_2022-05-05_00-26-rootfs.tar.zst"
old_sha256 = "73df33c38cff2b0c2e86cf1680576863decc4abb27197403c0f2fedb2433561d"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kinetic_arm64_2022-05-07_00-10-rootfs.tar.zst
# SHA256SUM=4780171df8810ebc66a3bd8c003c39d19894deace3fe8283f56a275eb16386eb
# BUILD_DATE=20220507
# BUILD_TAG=2022-05-07
# STATUS=completed
# VERSION=latest01
# END_TIME=00:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-07
begin = 2022-05-07 00:04:27.161798219+00:00
start-sync_0 = 00:08:50
start-zstd = 00:09:13
start-sync_1 = 00:10:28
end-sync_1 = 00:10:37
end = 2022-05-07 00:10:37.423728455+00:00

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
