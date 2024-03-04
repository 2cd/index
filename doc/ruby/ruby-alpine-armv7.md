# ruby-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-armv7 \
    cake233/ruby-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-armv7 bash
```

## ruby-alpine-armv7.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2024-03-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_armhf_2024-03-04_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "85a1b98250a1e59876176bc46598a1430a4d86df5c4ac66675960bc2cd8429d0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "81M"
tar_bytes = 84838912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 38683580

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "ruby-musl_armhf_2023-11-20_12-05-rootfs.tar.zst"
previous_sha256 = "4999e1febd48771285368526a6a25d8678d041ca781495858daa7d9389ad4453"

current_version = "latest01"
current_date = "20240304"
old_file = "ruby-musl_armhf_2023-10-23_12-05-rootfs.tar.zst"
old_sha256 = "36b119a2577045f9e849dd32a4d7b0b9299576805dfacd62e796a06e10736e81"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2024-03-04_12-04-rootfs.tar.zst
# SHA256SUM=85a1b98250a1e59876176bc46598a1430a4d86df5c4ac66675960bc2cd8429d0
# BUILD_DATE=20240304
# BUILD_TAG=2024-03-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-04
begin = 2024-03-04 12:02:34.381575793+00:00
start-sync_0 = 12:03:45
start-zstd = 12:03:51
start-sync_1 = 12:04:26
end-sync_1 = 12:04:32
end = 2024-03-04 12:04:32.661648913+00:00

[server]
repo = "cake233/ruby-alpine-armv7"

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
LANG = "C.UTF-8"
PATH = "/usr/local/bundle/bin${PATH:+:${PATH}}"
GEM_HOME = '/usr/local/bundle'
BUNDLE_SILENCE_ROOT_WARNING = '1'
BUNDLE_APP_CONFIG = '/usr/local/bundle'

[version]
ldd = 'musl libc (armhf) Version 1.2.4_git20230717'
ruby = 'ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [arm-linux-musleabihf]'
gem = '3.5.3'
bundle = 'Bundler version 2.5.3'
```
