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
tag = ["alpine", "2022-06-06", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2022-06-06_12-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "61795272ee58637469e5245db30803005a983a37b45e06c5334ad8a95abb0e82"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "83M"
tar_bytes = 86334464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "33M"
zstd_bytes = 33797069

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220523"
previous_tag = "2022-05-23"
previous_file = "ruby-musl_amd64_2022-05-23_12-04-rootfs.tar.zst"
previous_sha256 = "1d23fdd35554ae6059fcdd50ba56dc9f2ce702c618d123cc075146a5706f3332"

current_version = "latest01"
current_date = "20220606"
old_file = "ruby-musl_amd64_2022-05-09_12-03-rootfs.tar.zst"
old_sha256 = "31315e4b9cc47c48d48bf6cbd038f9dc05c62cd337da00a35de865a6d0d5b93d"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2022-06-06_12-04-rootfs.tar.zst
# SHA256SUM=61795272ee58637469e5245db30803005a983a37b45e06c5334ad8a95abb0e82
# BUILD_DATE=20220606
# BUILD_TAG=2022-06-06
# STATUS=completed
# VERSION=latest01
# END_TIME=12:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-06
begin = 2022-06-06 12:02:33.941347648+00:00
start-sync_0 = 12:03:16
start-zstd = 12:03:24
start-sync_1 = 12:04:07
end-sync_1 = 12:04:14
end = 2022-06-06 12:04:14.557086634+00:00

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
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x86_64-linux-musl]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
