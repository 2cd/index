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
tag = ["alpine", "2023-02-27", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2023-02-27_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f85b66dc57c7ff0ea9f8cf4445ccd8ea4121cbb2f3641be74c5aee498c56169b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "89M"
tar_bytes = 93166080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "37M"
zstd_bytes = 37913750

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230213"
previous_tag = "2023-02-13"
previous_file = "ruby-musl_amd64_2023-02-13_12-03-rootfs.tar.zst"
previous_sha256 = "1b66610b910e00b593c3a47feab4a9c347085f5ab3d152a29920758b92641a9f"

current_version = "latest01"
current_date = "20230227"
old_file = "ruby-musl_amd64_2023-01-30_12-04-rootfs.tar.zst"
old_sha256 = "57908e3e44464248dcc6500b6be0cfc9f3b1dab2c34d17b89f11921151de98d2"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2023-02-27_12-04-rootfs.tar.zst
# SHA256SUM=f85b66dc57c7ff0ea9f8cf4445ccd8ea4121cbb2f3641be74c5aee498c56169b
# BUILD_DATE=20230227
# BUILD_TAG=2023-02-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-27
begin = 2023-02-27 12:02:38.762047282+00:00
start-sync_0 = 12:03:14
start-zstd = 12:03:20
start-sync_1 = 12:04:05
end-sync_1 = 12:04:12
end = 2023-02-27 12:04:12.209033753+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.3'
ruby = 'ruby 3.2.1 (2023-02-08 revision 31819e82c8) [x86_64-linux-musl]'
gem = '3.4.6'
bundle = 'Bundler version 2.4.6'
```
