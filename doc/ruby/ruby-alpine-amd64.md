# ruby-alpine-amd64

## How to run it?

```shell
docker run \
    -it \
    --name ruby-alpine-amd64 \
    cake233/ruby-alpine-amd64
```

## How to exec shell?

```shell
    docker exec -it ruby-alpine-amd64 bash
```

## ruby-alpine-amd64.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2021-11-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ruby-musl_amd64_2021-11-28_22-40.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c81a5631af0f909ce5bbc94b8554218614c0b1ed2e8177437c42f6d4070f5ee0"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "76M"
tar_bytes = 79244288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "32M"
zstd_bytes = 32556690

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211128"
last_tag = ""
last_file = ""

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby-musl_amd64_2021-11-28_22-40.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=22:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:39:47.687265107+00:00
start-sync_0 = 22:40:02
start-zstd = 22:40:09
start-sync_1 = 22:40:22
end-sync_1 = 22:40:29
end = 2021-11-28 22:40:29.780702501+00:00

[server]
repo = "cake233/ruby-alpine-amd64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
ruby = 'ruby 3.0.3p157 (2021-11-24 revision 3fb7d2cadc) [x86_64-linux-musl]'
gem = '3.2.32'
bundle = 'Bundler version 2.2.32'
```
