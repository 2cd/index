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
tag = ["alpine", "2022-02-14", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ruby-musl_amd64_2022-02-14_12-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "304d3cf2dd0c03fb4ec372eda8f9d01bc56fdec51d6c7b9519d02891836a870a"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "81M"
tar_bytes = 84875264

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 34289371

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220117"
previous_tag = "2022-01-17"
previous_file = "ruby-musl_amd64_2022-01-17_12-03-rootfs.tar.zst"
previous_sha256 = "678f41647e806395dd223ac69891a4173d0df18aa81544b5e1fc588167946a06"

current_version = "latest02"
current_date = "20220214"
old_file = "ruby-musl_amd64_2022-01-03_12-03-rootfs.tar.zst"
old_sha256 = "7f161035494db7e62b0579a7aa059c5e333d19f0e0c579b6b60a01cfaf053a81"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2022-02-14_12-03-rootfs.tar.zst
# SHA256SUM=304d3cf2dd0c03fb4ec372eda8f9d01bc56fdec51d6c7b9519d02891836a870a
# BUILD_DATE=20220214
# BUILD_TAG=2022-02-14
# STATUS=completed
# VERSION=latest02
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-14
begin = 2022-02-14 12:02:29.109948963+00:00
start-sync_0 = 12:03:04
start-zstd = 12:03:11
start-sync_1 = 12:03:25
end-sync_1 = 12:03:31
end = 2022-02-14 12:03:31.545349707+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.2'
ruby = 'ruby 3.1.0p0 (2021-12-25 revision fb4df44d16) [x86_64-linux-musl]'
gem = '3.3.3'
bundle = 'Bundler version 2.3.3'
```
