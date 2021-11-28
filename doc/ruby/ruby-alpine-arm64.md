# ruby-alpine-arm64

## How to run it?

```shell
docker run \
    -it \
    --name ruby-alpine-arm64 \
    cake233/ruby-alpine-arm64
```

## How to exec shell?

```shell
    docker exec -it ruby-alpine-arm64 bash
```

## ruby-alpine-arm64.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2021-11-28", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "ruby-musl_arm64_2021-11-28_22-41.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "c636084ee5bd80165dae71ca6ba52dd14da471f3cacff0aff08828a48e7b9818"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "75M"
tar_bytes = 77740544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "31M"
zstd_bytes = 32006679

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211109"
last_tag = ""
last_file = "ruby_arm64+alpine-2021_11-09-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2021-11-28_22-41.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest02
# END_TIME=22:41

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 22:40:00.716035075+00:00
start-sync_0 = 22:40:33
start-zstd = 22:40:42
start-sync_1 = 22:40:54
end-sync_1 = 22:41:04
end = 2021-11-28 22:41:04.122253479+00:00

[server]
repo = "cake233/ruby-alpine-arm64"

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
ruby = 'ruby 3.0.3p157 (2021-11-24 revision 3fb7d2cadc) [aarch64-linux-musl]'
gem = '3.2.32'
bundle = 'Bundler version 2.2.32'
```
