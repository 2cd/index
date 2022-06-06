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
tag = ["latest", "2022-06-06"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2022-06-06_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "de87069e2b5470e2c1c12b72de2ee66e4463659560ef22e3b8c8e83270f8fc99"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "895M"
tar_bytes = 937900544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208248842

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220523"
previous_tag = "2022-05-23"
previous_file = "ruby_amd64_2022-05-23_12-11-rootfs.tar.zst"
previous_sha256 = "9b7f4dd6277fee54a22d5d37cec77a6a7036cd4759e8a51d03a1b5841b188504"

current_version = "latest02"
current_date = "20220606"
old_file = "ruby_amd64_2022-05-09_12-13-rootfs.tar.zst"
old_sha256 = "533760a42cfb2fa55d5eb56cb94438b7da6569246adfd3e42668d00b4e48abbc"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2022-06-06_12-13-rootfs.tar.zst
# SHA256SUM=de87069e2b5470e2c1c12b72de2ee66e4463659560ef22e3b8c8e83270f8fc99
# BUILD_DATE=20220606
# BUILD_TAG=2022-06-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-06
begin = 2022-06-06 12:02:34.108824931+00:00
start-sync_0 = 12:03:33
start-zstd = 12:04:55
start-sync_1 = 12:13:39
end-sync_1 = 12:13:59
end = 2022-06-06 12:13:59.344960111+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x86_64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
