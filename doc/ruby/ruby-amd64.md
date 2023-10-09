# ruby-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-amd64 \
    cake233/ruby-amd64
```

## How to exec shell?

```sh
docker exec -it ruby-amd64 bash
```

## ruby-amd64.toml

```toml
[main]
name = "ruby"
tag = ["latest", "2023-10-09"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2023-10-09_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "72ba21dcc6c7c495e3ef2b47bb38501044344bf7afc96cc652e4ce7729a3ead3"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "989M"
tar_bytes = 1036754944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "214M"
zstd_bytes = 223737698

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230925"
previous_tag = "2023-09-25"
previous_file = "ruby_amd64_2023-09-25_12-10-rootfs.tar.zst"
previous_sha256 = "2a235de1ff842338c1e667c606c214520cf3b461db88503b7ffa99b05593e634"

current_version = "latest02"
current_date = "20231009"
old_file = "ruby_amd64_2023-09-11_12-09-rootfs.tar.zst"
old_sha256 = "773b81bcb449347ac211974ca784896a73680f74d0ad5441f813e6e797d57206"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2023-10-09_12-11-rootfs.tar.zst
# SHA256SUM=72ba21dcc6c7c495e3ef2b47bb38501044344bf7afc96cc652e4ce7729a3ead3
# BUILD_DATE=20231009
# BUILD_TAG=2023-10-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-09
begin = 2023-10-09 12:02:40.124588100+00:00
start-sync_0 = 12:04:35
start-zstd = 12:05:55
start-sync_1 = 12:11:09
end-sync_1 = 12:11:36
end = 2023-10-09 12:11:36.117471510+00:00

[server]
repo = "cake233/ruby-amd64"

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
PATH = "/usr/local/bundle/bin${PATH:+:${PATH}}"
GEM_HOME = '/usr/local/bundle'
BUNDLE_SILENCE_ROOT_WARNING = '1'
BUNDLE_APP_CONFIG = '/usr/local/bundle'

[version]
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x86_64-linux]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
