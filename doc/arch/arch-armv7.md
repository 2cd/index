# arch-armv7

## How to run it?

```sh
docker run \
    -it \
    --name arch-armv7 \
    cake233/arch-armv7
```

## How to exec shell?

```sh
docker exec -it arch-armv7 sh
```

## arch-armv7.toml

```toml
[main]
name = "arch"
tag = ["base", "2023-05-31"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "arch_armhf_2023-05-31_00-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "029d7ddc4c004ba3583bea505b01b78af6c9ea41347170e3d68232460195b0e0"

# zstd: [1-22]
zstd-level = 12

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "807M"
tar_bytes = 845547520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "239M"
zstd_bytes = 250001347

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230531"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch_armhf_2023-05-31_00-07-rootfs.tar.zst
# SHA256SUM=029d7ddc4c004ba3583bea505b01b78af6c9ea41347170e3d68232460195b0e0
# BUILD_DATE=20230531
# BUILD_TAG=2023-05-31
# STATUS=completed
# VERSION=latest01
# END_TIME=00:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-31
begin = 2023-05-31 00:02:31.111334638+00:00
start-sync_0 = 00:05:46
start-zstd = 00:06:27
start-sync_1 = 00:06:46
end-sync_1 = 00:07:08
end = 2023-05-31 00:07:08.667664265+00:00

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
current = true
previous = false
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
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
