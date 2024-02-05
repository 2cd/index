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
tag = ["latest", "2024-02-05"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2024-02-05_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "bad40c78e6d4beae05df1751581a8a644bd794052bbed1cb0085668703f5b1c0"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "992M"
tar_bytes = 1039549952

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 225678145

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "ruby_amd64_2023-11-20_12-10-rootfs.tar.zst"
previous_sha256 = "f3d3cfc6acd5935a20bc580c3fc40e2c42fba880d1f94a815f29e8a01a8c0b31"

current_version = "latest01"
current_date = "20240205"
old_file = "ruby_amd64_2023-10-23_12-12-rootfs.tar.zst"
old_sha256 = "188aa5c4098f1dab03f3ff36a070a07e797d4fcc0c7fdb8eca8bb2d1f6ef4c93"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2024-02-05_12-11-rootfs.tar.zst
# SHA256SUM=bad40c78e6d4beae05df1751581a8a644bd794052bbed1cb0085668703f5b1c0
# BUILD_DATE=20240205
# BUILD_TAG=2024-02-05
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-05
begin = 2024-02-05 12:02:36.298233070+00:00
start-sync_0 = 12:04:19
start-zstd = 12:05:51
start-sync_1 = 12:10:47
end-sync_1 = 12:11:00
end = 2024-02-05 12:11:00.414306421+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u4) 2.36'
ruby = 'ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [x86_64-linux]'
gem = '3.5.3'
bundle = 'Bundler version 2.5.3'
```
