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
tag = ["alpine", "2024-01-08", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_amd64_2024-01-08_12-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2a71eb9453832de9b30039c6367200759456142514905bae58ffae2d219f3fad"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "95M"
tar_bytes = 99449344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "41M"
zstd_bytes = 42580836

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240108"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2024-01-08_12-03-rootfs.tar.zst
# SHA256SUM=2a71eb9453832de9b30039c6367200759456142514905bae58ffae2d219f3fad
# BUILD_DATE=20240108
# BUILD_TAG=2024-01-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-08
begin = 2024-01-08 12:02:36.651065344+00:00
start-sync_0 = 12:02:52
start-zstd = 12:03:01
start-sync_1 = 12:03:40
end-sync_1 = 12:03:50
end = 2024-01-08 12:03:50.887810988+00:00

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
ruby = 'ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [x86_64-linux-musl]'
gem = '3.5.3'
bundle = 'Bundler version 2.5.3'
```
