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
tag = ["kinetic", "2022-05-04", "devel"]
os = "ubuntu"
release = "dev"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ubuntu-kinetic_arm64_2022-05-04_00-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "006063ce6a399fffe422c623297ce1db23e3385aaf21165191aaaf07fdb75d09"

# zstd: [1-22]
zstd-level = 19

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "410M"
tar_bytes = 429006848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "69M"
zstd_bytes = 71672915

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220503"
previous_tag = "2022-05-03"
previous_file = "ubuntu-kinetic_arm64_2022-05-03_00-12-rootfs.tar.zst"
previous_sha256 = "86de3831f9298b8bcf437a70805e8077997d1ad56a7cd07c3cb722436b7a1ce1"

current_version = "latest02"
current_date = "20220504"
old_file = "ubuntu-kinetic_arm64_2022-05-02_00-12-rootfs.tar.zst"
old_sha256 = "97ef1f94f4dbb442cb349cbaa0a427d6a7df19849c12ca899aaef6f31dc9e678"
# edition 2021
# DISTRO_NAME=ubuntu-dev_arm64
# ROOTFS_FILE=ubuntu-kinetic_arm64_2022-05-04_00-12-rootfs.tar.zst
# SHA256SUM=006063ce6a399fffe422c623297ce1db23e3385aaf21165191aaaf07fdb75d09
# BUILD_DATE=20220504
# BUILD_TAG=2022-05-04
# STATUS=completed
# VERSION=latest02
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-04
begin = 2022-05-04 00:06:04.259778752+00:00
start-sync_0 = 00:10:33
start-zstd = 00:11:01
start-sync_1 = 00:12:20
end-sync_1 = 00:12:31
end = 2022-05-04 00:12:31.475274868+00:00

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
