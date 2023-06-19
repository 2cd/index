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
tag = ["latest", "2023-06-19"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2023-06-19_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e5e4376b891a37290e44ff6c6947957ea9c30416d2c4ed30d81cf25c74651aec"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "995M"
tar_bytes = 1042693632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 222163118

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230605"
previous_tag = "2023-06-05"
previous_file = "ruby_arm64_2023-06-05_12-11-rootfs.tar.zst"
previous_sha256 = "8a8d4ef0f23101b5c00a6b364ef456afac5424599e40c00bb856694e92a91837"

current_version = "latest02"
current_date = "20230619"
old_file = "ruby_arm64_2023-05-22_12-11-rootfs.tar.zst"
old_sha256 = "59a553cd1f692eb5bef9dfb72215487eba2c2399f23bf2237bb5b450d46f521b"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2023-06-19_12-11-rootfs.tar.zst
# SHA256SUM=e5e4376b891a37290e44ff6c6947957ea9c30416d2c4ed30d81cf25c74651aec
# BUILD_DATE=20230619
# BUILD_TAG=2023-06-19
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-19
begin = 2023-06-19 12:02:45.159613673+00:00
start-sync_0 = 12:06:19
start-zstd = 12:06:35
start-sync_1 = 12:11:32
end-sync_1 = 12:11:49
end = 2023-06-19 12:11:49.237394453+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [aarch64-linux]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
