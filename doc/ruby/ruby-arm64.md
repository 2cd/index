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
tag = ["latest", "2023-01-30"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2023-01-30_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "00fc293456a78b95ecb93c668c59b8ea1d4a30ae4617f7e21ce44f6a367c4c5d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "849M"
tar_bytes = 889581568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "201M"
zstd_bytes = 210215282

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230116"
previous_tag = "2023-01-16"
previous_file = "ruby_arm64_2023-01-16_12-10-rootfs.tar.zst"
previous_sha256 = "70957e6cea06e95d8ba9bdf2626e65d84cd8837f315ff6e44aee3a73f591a407"

current_version = "latest02"
current_date = "20230130"
old_file = "ruby_arm64_2023-01-02_12-10-rootfs.tar.zst"
old_sha256 = "783e1fd576f2f25ca212cf984732ea588cab7823bcef2e485d876b8eeee88e96"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2023-01-30_12-10-rootfs.tar.zst
# SHA256SUM=00fc293456a78b95ecb93c668c59b8ea1d4a30ae4617f7e21ce44f6a367c4c5d
# BUILD_DATE=20230130
# BUILD_TAG=2023-01-30
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-30
begin = 2023-01-30 12:02:35.405134343+00:00
start-sync_0 = 12:05:44
start-zstd = 12:06:03
start-sync_1 = 12:10:07
end-sync_1 = 12:10:23
end = 2023-01-30 12:10:23.151790656+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
ruby = 'ruby 3.2.0 (2022-12-25 revision a528908271) [aarch64-linux]'
gem = '3.4.1'
bundle = 'Bundler version 2.4.1'
```
