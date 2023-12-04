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
tag = ["latest", "2023-12-04"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2023-12-04_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b4eb6ca120c5429b21142ea1844480859bcceb744693c902da1b19d03bcfeb10"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "989M"
tar_bytes = 1036729344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "214M"
zstd_bytes = 223720286

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "ruby_amd64_2023-10-23_12-12-rootfs.tar.zst"
previous_sha256 = "188aa5c4098f1dab03f3ff36a070a07e797d4fcc0c7fdb8eca8bb2d1f6ef4c93"

current_version = "latest02"
current_date = "20231204"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2023-12-04_12-11-rootfs.tar.zst
# SHA256SUM=b4eb6ca120c5429b21142ea1844480859bcceb744693c902da1b19d03bcfeb10
# BUILD_DATE=20231204
# BUILD_TAG=2023-12-04
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-12-04
begin = 2023-12-04 12:02:35.822772664+00:00
start-sync_0 = 12:04:35
start-zstd = 12:06:36
start-sync_1 = 12:11:19
end-sync_1 = 12:11:33
end = 2023-12-04 12:11:33.476978114+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x86_64-linux]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```
