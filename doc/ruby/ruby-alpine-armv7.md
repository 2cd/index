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
tag = ["alpine", "2022-03-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ruby-musl_armhf_2022-03-01_18-55.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a04fbd5f5ff0de120b1dd85af835a615544bf1be857827c084f3c839dada42dc"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "72M"
tar_bytes = 75287040

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32343462

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220214"
previous_tag = "2022-02-14"
previous_file = "ruby-musl_armhf_2022-02-14_12-03-rootfs.tar.zst"
previous_sha256 = "3eb971200b0d7d2c93419dad764c43aeee1e87eb0cfd795c07a1f01c80ac6245"

current_version = "latest01"
current_date = "20220301"
old_file = "ruby-musl_armhf_2022-01-31_12-04-rootfs.tar.zst"
old_sha256 = "3476505d674445c9f52b05a8d9154326a1c5dcde73198c90c761902d76649086"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2022-03-01_18-55-rootfs.tar.zst
# SHA256SUM=a04fbd5f5ff0de120b1dd85af835a615544bf1be857827c084f3c839dada42dc
# BUILD_DATE=20220301
# BUILD_TAG=2022-03-01
# STATUS=completed
# VERSION=latest01
# END_TIME=18:55

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-01
begin = 2022-03-01 18:53:58.412524658+00:00
start-sync_0 = 18:54:56
start-zstd = 18:55:10
start-sync_1 = 18:55:21
end-sync_1 = 18:55:33
end = 2022-03-01 18:55:33.587489863+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (armhf) Version 1.2.2'
ruby = 'ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [arm-linux-musleabihf]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
