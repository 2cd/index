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
tag = ["latest", "2023-02-27"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2023-02-27_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3340fbe14ba261844a632576e71e7db8a509026f34af4091e9d3b8f321ddef16"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "896M"
tar_bytes = 938824704

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "202M"
zstd_bytes = 211364126

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230213"
previous_tag = "2023-02-13"
previous_file = "ruby_amd64_2023-02-13_12-11-rootfs.tar.zst"
previous_sha256 = "bd97758cb1abdf6104b4f8723c6593d1ec085a738ab585e0aba9ed4a3b74af9b"

current_version = "latest02"
current_date = "20230227"
old_file = "ruby_amd64_2023-01-30_12-15-rootfs.tar.zst"
old_sha256 = "bc8565516f125db877d166c37de5d221fb8f4f85f23505a640d4acb0c777a017"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2023-02-27_12-13-rootfs.tar.zst
# SHA256SUM=3340fbe14ba261844a632576e71e7db8a509026f34af4091e9d3b8f321ddef16
# BUILD_DATE=20230227
# BUILD_TAG=2023-02-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-27
begin = 2023-02-27 12:02:39.148445867+00:00
start-sync_0 = 12:03:38
start-zstd = 12:04:56
start-sync_1 = 12:12:57
end-sync_1 = 12:13:15
end = 2023-02-27 12:13:15.145124968+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
ruby = 'ruby 3.2.1 (2023-02-08 revision 31819e82c8) [x86_64-linux]'
gem = '3.4.6'
bundle = 'Bundler version 2.4.6'
```
