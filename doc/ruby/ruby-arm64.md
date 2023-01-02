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
tag = ["latest", "2023-01-02"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_arm64_2023-01-02_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "783e1fd576f2f25ca212cf984732ea588cab7823bcef2e485d876b8eeee88e96"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "844M"
tar_bytes = 884332032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 207223689

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221219"
previous_tag = "2022-12-19"
previous_file = "ruby_arm64_2022-12-19_12-11-rootfs.tar.zst"
previous_sha256 = "d23e5c95acdf8bdfa5a48fdd7730a9d624440b4ce8d22ecb9c61eb2c30072361"

current_version = "latest02"
current_date = "20230102"
old_file = "ruby_arm64_2022-11-21_12-10-rootfs.tar.zst"
old_sha256 = "b6b48929c009042951412df6f8d8dd9294ed47ba6d979ecd9de050c830b66d7c"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby_arm64_2023-01-02_12-10-rootfs.tar.zst
# SHA256SUM=783e1fd576f2f25ca212cf984732ea588cab7823bcef2e485d876b8eeee88e96
# BUILD_DATE=20230102
# BUILD_TAG=2023-01-02
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-02
begin = 2023-01-02 12:02:36.834555327+00:00
start-sync_0 = 12:05:43
start-zstd = 12:05:59
start-sync_1 = 12:10:14
end-sync_1 = 12:10:32
end = 2023-01-02 12:10:32.925586948+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
ruby = 'ruby 3.2.0 (2022-12-25 revision a528908271) [aarch64-linux]'
gem = '3.4.1'
bundle = 'Bundler version 2.4.1'
```
