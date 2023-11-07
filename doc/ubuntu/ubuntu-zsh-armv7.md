# ubuntu-zsh-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ubuntu-zsh-armv7 \
    cake233/ubuntu-zsh-armv7
```

## How to exec shell?

```sh
docker exec -it ubuntu-zsh-armv7 zsh
```

## ubuntu-zsh-armv7.toml

```toml
[main]
name = "ubuntu"
tag = ["zsh", "2023-11-07", "devel"]
os = "ubuntu"
release = "dev"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-zsh_armhf_2023-11-07_00-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fe98663fa637cba70599a4e64be84ed148152be855b8867a165fe50f4763bd70"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "707M"
tar_bytes = 740654080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "149M"
zstd_bytes = 155331535

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231024"
previous_tag = "2023-10-24"
previous_file = "ubuntu-zsh_armhf_2023-10-24_00-24-rootfs.tar.zst"
previous_sha256 = "aa74c8dd71e1a315a0c585b886259ab52dd8974b2b8813487929dd0f0af691f8"

current_version = "latest01"
current_date = "20231107"
old_file = "ubuntu-zsh_armhf_2023-10-17_00-21-rootfs.tar.zst"
old_sha256 = "dea7e395e90acf3b07fe5650ff661b09a2e321dc664efb061867b5788066d726"
# edition 2021
# DISTRO_NAME=ubuntu-dev_armhf
# ROOTFS_FILE=ubuntu-zsh_armhf_2023-11-07_00-16-rootfs.tar.zst
# SHA256SUM=fe98663fa637cba70599a4e64be84ed148152be855b8867a165fe50f4763bd70
# BUILD_DATE=20231107
# BUILD_TAG=2023-11-07
# STATUS=completed
# VERSION=latest01
# END_TIME=00:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-07
begin = 2023-11-07 00:02:29.631596070+00:00
start-sync_0 = 00:13:21
start-zstd = 00:14:56
start-sync_1 = 00:16:43
end-sync_1 = 00:16:58
end = 2023-11-07 00:16:58.156915873+00:00

[server]
repo = "cake233/ubuntu-zsh-armv7"

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
ldd = 'ldd (Ubuntu GLIBC 2.38-1ubuntu6) 2.38'
zsh = 'zsh 5.9 (arm-unknown-linux-gnueabihf)'
```
