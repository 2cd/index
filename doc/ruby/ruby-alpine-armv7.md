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
tag = ["alpine", "2023-07-17", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_armhf_2023-07-17_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9169110c6bcb956b6e950c4b7815be47b7ac5f03fea02a55b728e74f43c333cd"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "74M"
tar_bytes = 76961280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33825477

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230703"
previous_tag = "2023-07-03"
previous_file = "ruby-musl_armhf_2023-07-03_12-04-rootfs.tar.zst"
previous_sha256 = "82a7270a83ae4c245322e393a7fe72c008c5b49ff238d6c1221096d9c4d9f71a"

current_version = "latest01"
current_date = "20230717"
old_file = "ruby-musl_armhf_2023-06-19_12-05-rootfs.tar.zst"
old_sha256 = "b687d795574f35ed5685458814120083263ebe1f5ac41715b302a378eda5089c"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2023-07-17_12-04-rootfs.tar.zst
# SHA256SUM=9169110c6bcb956b6e950c4b7815be47b7ac5f03fea02a55b728e74f43c333cd
# BUILD_DATE=20230717
# BUILD_TAG=2023-07-17
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-17
begin = 2023-07-17 12:02:37.805816429+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:46
start-sync_1 = 12:04:20
end-sync_1 = 12:04:27
end = 2023-07-17 12:04:27.519099978+00:00

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
ldd = 'musl libc (armhf) Version 1.2.4'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [arm-linux-musleabihf]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
