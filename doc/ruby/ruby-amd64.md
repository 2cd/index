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
tag = ["latest", "2024-01-08"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2024-01-08_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6779157402fff2b1d0b230014449e226c89cefa9defa14b45384ccf246849001"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "992M"
tar_bytes = 1039545856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 225664881

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
# ROOTFS_FILE=ruby_amd64_2024-01-08_12-08-rootfs.tar.zst
# SHA256SUM=6779157402fff2b1d0b230014449e226c89cefa9defa14b45384ccf246849001
# BUILD_DATE=20240108
# BUILD_TAG=2024-01-08
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-08
begin = 2024-01-08 12:02:34.396828146+00:00
start-sync_0 = 12:03:09
start-zstd = 12:03:20
start-sync_1 = 12:08:29
end-sync_1 = 12:08:43
end = 2024-01-08 12:08:43.251658641+00:00

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
ruby = 'ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [x86_64-linux]'
gem = '3.5.3'
bundle = 'Bundler version 2.5.3'
```
