# ruby-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-amd64 \
    cake233/ruby-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-amd64 bash
```

## ruby-alpine-amd64.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2023-08-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2023-08-28_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d0b91b489423ecc1f1a1ddd544591490c91c7dde71cf8a699fdbacdd0b08a123"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "89M"
tar_bytes = 92880896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 37872328

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230828"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2023-08-28_12-03-rootfs.tar.zst
# SHA256SUM=d0b91b489423ecc1f1a1ddd544591490c91c7dde71cf8a699fdbacdd0b08a123
# BUILD_DATE=20230828
# BUILD_TAG=2023-08-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-28
begin = 2023-08-28 12:02:42.364426783+00:00
start-sync_0 = 12:02:55
start-zstd = 12:03:04
start-sync_1 = 12:03:46
end-sync_1 = 12:03:55
end = 2023-08-28 12:03:55.898733207+00:00

[server]
repo = "cake233/ruby-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.4'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x86_64-linux-musl]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```