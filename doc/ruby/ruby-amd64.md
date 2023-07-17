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
tag = ["latest", "2023-07-17"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2023-07-17_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e93f61ebc478a466ad2ae9b25ff1c6ef40fd461df48ddc6813978773b41dfb67"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "989M"
tar_bytes = 1036674048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "214M"
zstd_bytes = 223655374

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230703"
previous_tag = "2023-07-03"
previous_file = "ruby_amd64_2023-07-03_12-10-rootfs.tar.zst"
previous_sha256 = "121cdcdacb44958094fd90cb7eb6e8e6d9a8ad7f81d1dd46a2f6425d967450ed"

current_version = "latest02"
current_date = "20230717"
old_file = "ruby_amd64_2023-06-19_12-10-rootfs.tar.zst"
old_sha256 = "e3c0fb6f8fb53fa47356c15d882c779cec4af8c8be845f03b8eb92c0c3befe9d"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2023-07-17_12-10-rootfs.tar.zst
# SHA256SUM=e93f61ebc478a466ad2ae9b25ff1c6ef40fd461df48ddc6813978773b41dfb67
# BUILD_DATE=20230717
# BUILD_TAG=2023-07-17
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-17
begin = 2023-07-17 12:02:37.931411413+00:00
start-sync_0 = 12:03:41
start-zstd = 12:05:12
start-sync_1 = 12:10:30
end-sync_1 = 12:10:47
end = 2023-07-17 12:10:47.248191515+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x86_64-linux]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
