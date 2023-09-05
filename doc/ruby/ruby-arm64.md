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
tag = ["latest", "2023-08-28"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2023-08-28_12-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ab46467b5187a9bb6459e2fb767108ba5fd63aa9868f1374f9f18282c5ca511b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "995M"
tar_bytes = 1042714624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "212M"
zstd_bytes = 222225786

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230828"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2023-08-28_12-14-rootfs.tar.zst
# SHA256SUM=ab46467b5187a9bb6459e2fb767108ba5fd63aa9868f1374f9f18282c5ca511b
# BUILD_DATE=20230828
# BUILD_TAG=2023-08-28
# STATUS=completed
# VERSION=latest01
# END_TIME=12:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-28
begin = 2023-08-28 12:02:41.683624220+00:00
start-sync_0 = 12:06:36
start-zstd = 12:06:52
start-sync_1 = 12:13:41
end-sync_1 = 12:14:01
end = 2023-08-28 12:14:01.416805486+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u1) 2.36'
ruby = 'ruby 3.2.2 (2023-03-30 revision e51014f9c0) [aarch64-linux]'
gem = '3.4.10'
bundle = 'Bundler version 2.4.10'
```