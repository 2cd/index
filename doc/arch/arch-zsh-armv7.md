# arch-zsh-armv7

## How to run it?

```shell
docker run \
    -it \
    --name arch-zsh-armv7 \
    cake233/arch-zsh-armv7
```

## How to exec shell?

```shell
    docker exec -it arch-zsh-armv7 zsh
```

## arch-zsh-armv7.toml

```toml
[main]
name = "arch"
tag = ["zsh", "2021-12-08"]
os = "arch"
release = "latest"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "arch-zsh_armhf_2021-12-08_00-24.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "306e6a264f1039e9b62a8ab15160080d6e82e7133ea9b60a0024c18b872559ed"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "847M"
tar_bytes = 887872512

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "207M"
zstd_bytes = 216026857

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211201"
last_tag = "2021-12-01"
last_file = "arch-zsh_armhf_2021-12-01_00-21-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest01"
current_date = "20211208"
old_file = "arch-zsh_armhf_2021-11-28_23-26-rootfs.tar.zst"
old_sha256 = ""
# edition 2021
# DISTRO_NAME=arch_armhf
# ROOTFS_FILE=arch-zsh_armhf_2021-12-08_00-24-rootfs.tar.zst
# SHA256SUM=306e6a264f1039e9b62a8ab15160080d6e82e7133ea9b60a0024c18b872559ed
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest01
# END_TIME=00:24

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 00:06:13.451664033+00:00
start-sync_0 = 00:18:27
start-zstd = 00:20:11
start-sync_1 = 00:24:01
end-sync_1 = 00:24:25
end = 2021-12-08 00:24:25.589328588+00:00

[server]
repo = "cake233/arch-zsh-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
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
