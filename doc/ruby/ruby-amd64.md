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
tag = ["latest", "2022-05-09"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby_amd64_2022-05-09_12-13.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "533760a42cfb2fa55d5eb56cb94438b7da6569246adfd3e42668d00b4e48abbc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "895M"
tar_bytes = 937548288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 208009822

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220425"
previous_tag = "2022-04-25"
previous_file = "ruby_amd64_2022-04-25_12-11-rootfs.tar.zst"
previous_sha256 = "7850aebfa3a2b43ab52bfa749265b39db2512bd4b900f2b947423e682778dfd0"

current_version = "latest02"
current_date = "20220509"
old_file = "ruby_amd64_2022-04-11_11-16-rootfs.tar.zst"
old_sha256 = "0988899c205c7feeb9fed53cf89687cd1a5aa84c2d763c53af3fd72d7ce616fc"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2022-05-09_12-13-rootfs.tar.zst
# SHA256SUM=533760a42cfb2fa55d5eb56cb94438b7da6569246adfd3e42668d00b4e48abbc
# BUILD_DATE=20220509
# BUILD_TAG=2022-05-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-09
begin = 2022-05-09 12:02:35.406871715+00:00
start-sync_0 = 12:03:54
start-zstd = 12:05:36
start-sync_1 = 12:12:58
end-sync_1 = 12:13:14
end = 2022-05-09 12:13:14.989697362+00:00

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
