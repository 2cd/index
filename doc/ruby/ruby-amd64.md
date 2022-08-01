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
tag = ["latest", "2022-08-01"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2022-08-01_12-14.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5fc9d1790c61bbe90e91896300c348b6283f144ef88b3565e8758739371f5589"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "895M"
tar_bytes = 937937920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208251604

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "ruby_amd64_2022-07-04_12-14-rootfs.tar.zst"
previous_sha256 = "8c6c341092695c1fd39748e2702bdc8375d36f3cf36618cfc0444dcc66b78e78"

current_version = "latest01"
current_date = "20220801"
old_file = "ruby_amd64_2022-06-20_12-14-rootfs.tar.zst"
old_sha256 = "52e5339135246d09ae35cf1cadc273f93ece1c3402fd4acea3b8f7f15141b16e"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2022-08-01_12-14-rootfs.tar.zst
# SHA256SUM=5fc9d1790c61bbe90e91896300c348b6283f144ef88b3565e8758739371f5589
# BUILD_DATE=20220801
# BUILD_TAG=2022-08-01
# STATUS=completed
# VERSION=latest01
# END_TIME=12:14

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-01
begin = 2022-08-01 12:02:38.950058076+00:00
start-sync_0 = 12:04:28
start-zstd = 12:06:20
start-sync_1 = 12:14:04
end-sync_1 = 12:14:21
end = 2022-08-01 12:14:21.572832734+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x86_64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
