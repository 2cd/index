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
tag = ["latest", "2022-03-14"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ruby_arm64_2022-03-14_12-10.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "bee6adb337d8db011540cb20885637f1dbfebd3dfab0c60dc1c26dfa9ba32b31"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "847M"
tar_bytes = 887348224

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 206081132

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "ruby_arm64_2022-03-01_18-59-rootfs.tar.zst"
previous_sha256 = "eff73720eb4304d375b46ef7ca28c8002ca413673f330812385404cdddb10397"

current_version = "latest01"
current_date = "20220314"
old_file = "ruby_arm64_2022-02-14_12-08-rootfs.tar.zst"
old_sha256 = "d9a33ac968ce0acfc8097bfdf1a564f0862dc9de4429d4fe9e6eb31c2b8e8efd"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2022-03-14_12-10-rootfs.tar.zst
# SHA256SUM=bee6adb337d8db011540cb20885637f1dbfebd3dfab0c60dc1c26dfa9ba32b31
# BUILD_DATE=20220314
# BUILD_TAG=2022-03-14
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-14
begin = 2022-03-14 12:02:32.265008512+00:00
start-sync_0 = 12:05:07
start-zstd = 12:05:24
start-sync_1 = 12:09:53
end-sync_1 = 12:10:18
end = 2022-03-14 12:10:18.553628179+00:00

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/bundle/bin${PATH:+:${PATH}}"
GEM_HOME = '/usr/local/bundle'
BUNDLE_SILENCE_ROOT_WARNING = '1'
BUNDLE_APP_CONFIG = '/usr/local/bundle'

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
ruby = 'ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [aarch64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
