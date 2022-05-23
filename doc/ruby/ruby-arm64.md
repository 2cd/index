# ruby-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-arm64 \
    cake233/ruby-arm64
```

## How to exec shell?

```sh
docker exec -it ruby-arm64 bash
```

## ruby-arm64.toml

```toml
[main]
name = "ruby"
tag = ["latest", "2022-05-23"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2022-05-23_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "747e52805ad45d4c09140bc3b3b6dd333b8e0f7a8b06b3cd166a2dee6d9cd5ae"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "847M"
tar_bytes = 887438848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 206068692

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220509"
previous_tag = "2022-05-09"
previous_file = "ruby_arm64_2022-05-09_12-11-rootfs.tar.zst"
previous_sha256 = "3f3380e6d6fd574247e7f48aa5e1bdf24daaeab78131a18341d8158db7b8adc3"

current_version = "latest01"
current_date = "20220523"
old_file = "ruby_arm64_2022-04-25_12-11-rootfs.tar.zst"
old_sha256 = "606eb8a34d2367657a58dab67b603b975ffd229ca9af410d71f3958b6c7b5a20"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2022-05-23_12-12-rootfs.tar.zst
# SHA256SUM=747e52805ad45d4c09140bc3b3b6dd333b8e0f7a8b06b3cd166a2dee6d9cd5ae
# BUILD_DATE=20220523
# BUILD_TAG=2022-05-23
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-23
begin = 2022-05-23 12:02:37.170814069+00:00
start-sync_0 = 12:06:02
start-zstd = 12:06:28
start-sync_1 = 12:11:38
end-sync_1 = 12:12:03
end = 2022-05-23 12:12:03.463269470+00:00

[server]
repo = "cake233/ruby-arm64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [aarch64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
