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
tag = ["alpine", "2022-02-14", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "ruby-musl_armhf_2022-02-14_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3eb971200b0d7d2c93419dad764c43aeee1e87eb0cfd795c07a1f01c80ac6245"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "71M"
tar_bytes = 73775104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 31939849

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220131"
previous_tag = "2022-01-31"
previous_file = "ruby-musl_armhf_2022-01-31_12-04-rootfs.tar.zst"
previous_sha256 = "3476505d674445c9f52b05a8d9154326a1c5dcde73198c90c761902d76649086"

current_version = "latest02"
current_date = "20220214"
old_file = "ruby-musl_armhf_2022-01-17_12-04-rootfs.tar.zst"
old_sha256 = "e1c6f0859b0bbbb935466f0bc8cc63127bdd4f67851e5060c83df27ac71cf828"
# edition 2021
# DISTRO_NAME=ruby_armhf
# ROOTFS_FILE=ruby-musl_armhf_2022-02-14_12-03-rootfs.tar.zst
# SHA256SUM=3eb971200b0d7d2c93419dad764c43aeee1e87eb0cfd795c07a1f01c80ac6245
# BUILD_DATE=20220214
# BUILD_TAG=2022-02-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-14
begin = 2022-02-14 12:02:30.368590381+00:00
start-sync_0 = 12:03:23
start-zstd = 12:03:32
start-sync_1 = 12:03:42
end-sync_1 = 12:03:52
end = 2022-02-14 12:03:52.113267512+00:00

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
ruby = 'ruby 3.1.0p0 (2021-12-25 revision fb4df44d16) [arm-linux-musleabihf]'
gem = '3.3.3'
bundle = 'Bundler version 2.3.3'
```
