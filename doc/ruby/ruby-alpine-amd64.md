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
tag = ["alpine", "2023-12-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2023-12-18_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7c7f0706f0a1f03041bb590ed01542f98ecf2d547a891f8f0178c215fe9f82a5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "93M"
tar_bytes = 96475136

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "39M"
zstd_bytes = 40775305

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "ruby-musl_amd64_2023-10-23_12-05-rootfs.tar.zst"
previous_sha256 = "6a22a370509f3b74b5badfc9645de401ddcd37e90103135599bfbfc37ec6c7ef"

current_version = "latest02"
current_date = "20231218"
old_file = "ruby-musl_amd64_2023-10-09_12-04-rootfs.tar.zst"
old_sha256 = "032213458bd2ffa33461fb48d6d924c3c30e29cde8e10ca23694322ee018b0b7"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2023-12-18_12-05-rootfs.tar.zst
# SHA256SUM=7c7f0706f0a1f03041bb590ed01542f98ecf2d547a891f8f0178c215fe9f82a5
# BUILD_DATE=20231218
# BUILD_TAG=2023-12-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-18
begin = 2023-12-18 12:02:36.767275445+00:00
start-sync_0 = 12:04:15
start-zstd = 12:04:25
start-sync_1 = 12:05:02
end-sync_1 = 12:05:12
end = 2023-12-18 12:05:12.600996429+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x86_64-linux-musl]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
