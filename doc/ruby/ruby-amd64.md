# ruby-amd64

## How to run it?

```shell
docker run \
    -it \
    --name ruby-amd64 \
    cake233/ruby-amd64
```

## How to exec shell?

```shell
    docker exec -it ruby-amd64 bash
```

## ruby-amd64.toml

```toml
[main]
name = "ruby"
tag = ["latest", "2021-12-06"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "ruby_amd64_2021-12-06_20-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "04bfa022a49103a853bf97aa3b93528d8a0f6b3a85da450b582f5f4a07ab435a"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "885M"
tar_bytes = 927585280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "233M"
zstd_bytes = 243356788

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211128"
previous_tag = "2021-11-28"
previous_file = "ruby_amd64_2021-11-28_23-08-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211206"
old_file = ""
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2021-12-06_20-08-rootfs.tar.zst
# BUILD_DATE=20211206
# BUILD_TAG=2021-12-06
# STATUS=completed
# VERSION=latest02
# END_TIME=20:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-06
begin = 2021-12-06 20:04:29.866406624+00:00
start-sync_0 = 20:05:33
start-zstd = 20:05:51
start-sync_1 = 20:08:06
end-sync_1 = 20:08:30
end = 2021-12-06 20:08:30.480443797+00:00

[server]
repo = "cake233/ruby-amd64"

[server.node1]
name = "cn"
current = false
previous = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "global"
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
ruby = 'ruby 3.0.3p157 (2021-11-24 revision 3fb7d2cadc) [x86_64-linux]'
gem = '3.2.32'
bundle = 'Bundler version 2.2.32'
```
