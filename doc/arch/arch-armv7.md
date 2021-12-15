# arch-armv7

## How to run it?

```shell
docker run \
    -it \
    --name arch-armv7 \
    cake233/arch-armv7
```

## How to exec shell?

```shell
    docker exec -it arch-armv7 sh
```

## arch-armv7.toml

```toml
[main]
name = "arch"
tag = ["base", "2021-12-15"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch_armhf_2021-12-15_00-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f35cecdb1762989720ab326645c36ae2ce02d00432b64163988106e3a3b7f453"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "560M"
tar_bytes = 586356224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "167M"
zstd_bytes = 174425391

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20211215"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2021-12-15_00-05-rootfs.tar.zst
# SHA256SUM=f35cecdb1762989720ab326645c36ae2ce02d00432b64163988106e3a3b7f453
# BUILD_DATE=20211215
# BUILD_TAG=2021-12-15
# STATUS=completed
# VERSION=latest01
# END_TIME=00:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-15
begin = 2021-12-15 00:02:28.913867501+00:00
start-sync_0 = 00:03:56
start-zstd = 00:04:39
start-sync_1 = 00:04:50
end-sync_1 = 00:05:09
end = 2021-12-15 00:05:09.279766647+00:00

[server]
repo = "cake233/arch-armv7"

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
