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
tag = ["latest", "2022-09-26"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2022-09-26_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5105571bb11e0053ac810c95bf2ba58eaafa10dc9c8cee2a69724a0849959430"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "895M"
tar_bytes = 938294272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208341927

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220912"
previous_tag = "2022-09-12"
previous_file = "ruby_amd64_2022-09-12_12-13-rootfs.tar.zst"
previous_sha256 = "a9cee34bbfee3218cb1c766dc519018522e7b4e2e8c30ba278e289f486c7cf35"

current_version = "latest02"
current_date = "20220926"
old_file = "ruby_amd64_2022-08-29_12-14-rootfs.tar.zst"
old_sha256 = "2288f466615c7e29771a2702fbdd83fb7afa45f7ceb35ac19c8a5ac850b844b4"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2022-09-26_12-13-rootfs.tar.zst
# SHA256SUM=5105571bb11e0053ac810c95bf2ba58eaafa10dc9c8cee2a69724a0849959430
# BUILD_DATE=20220926
# BUILD_TAG=2022-09-26
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-26
begin = 2022-09-26 12:02:29.758561824+00:00
start-sync_0 = 12:04:16
start-zstd = 12:05:46
start-sync_1 = 12:13:21
end-sync_1 = 12:13:41
end = 2022-09-26 12:13:41.135624745+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u4) 2.31'
ruby = 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x86_64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
