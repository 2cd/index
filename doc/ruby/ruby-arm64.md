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
tag = ["latest", "2022-09-12"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2022-09-12_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d9b3b52e6fcde36e2fc0534a5c2bb714ee2f324ae84868f954b8d89c3f6e6ab6"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "847M"
tar_bytes = 887932416

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 206363687

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220829"
previous_tag = "2022-08-29"
previous_file = "ruby_arm64_2022-08-29_12-12-rootfs.tar.zst"
previous_sha256 = "d84513d794a2e88da17b954b1181173dc9b765d57b306d756aa83587ca9863a8"

current_version = "latest01"
current_date = "20220912"
old_file = "ruby_arm64_2022-08-15_12-10-rootfs.tar.zst"
old_sha256 = "9b139aca057ffd7f00a9c71158b39d584a5242770b8066cccbee8e4b5b8fce06"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2022-09-12_12-12-rootfs.tar.zst
# SHA256SUM=d9b3b52e6fcde36e2fc0534a5c2bb714ee2f324ae84868f954b8d89c3f6e6ab6
# BUILD_DATE=20220912
# BUILD_TAG=2022-09-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-12
begin = 2022-09-12 12:02:29.253639166+00:00
start-sync_0 = 12:06:40
start-zstd = 12:06:59
start-sync_1 = 12:12:03
end-sync_1 = 12:12:20
end = 2022-09-12 12:12:20.945060989+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [aarch64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
