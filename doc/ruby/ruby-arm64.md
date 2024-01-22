# ruby-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-arm64 \
    cake233/ruby-arm64
```

## How to exec shell?

```sh
docker exec -it ruby-arm64 bash
```

## ruby-arm64.toml

```toml
[main]
name = "ruby"
tag = ["latest", "2024-01-22"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2024-01-22_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4f34c62ec15a9c540fa0d032b6656eaa51deb04112b468aca028f67f91f2a7fd"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "998M"
tar_bytes = 1045496832

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "214M"
zstd_bytes = 224278121

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "ruby_arm64_2023-10-23_12-12-rootfs.tar.zst"
previous_sha256 = "dc10cb4964874666f78ea7f2b63dbc511685585218759a918b0903279fb55026"

current_version = "latest02"
current_date = "20240122"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2024-01-22_12-11-rootfs.tar.zst
# SHA256SUM=4f34c62ec15a9c540fa0d032b6656eaa51deb04112b468aca028f67f91f2a7fd
# BUILD_DATE=20240122
# BUILD_TAG=2024-01-22
# STATUS=completed
# VERSION=latest02
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-22
begin = 2024-01-22 12:02:35.519610051+00:00
start-sync_0 = 12:06:14
start-zstd = 12:06:25
start-sync_1 = 12:11:13
end-sync_1 = 12:11:28
end = 2024-01-22 12:11:28.667786182+00:00

[server]
repo = "cake233/ruby-arm64"

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
ruby = 'ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [aarch64-linux]'
gem = '3.5.3'
bundle = 'Bundler version 2.5.3'
```
