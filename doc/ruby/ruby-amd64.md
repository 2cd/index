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
tag = ["latest", "2022-04-11"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "ruby_amd64_2022-04-11_11-16.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0988899c205c7feeb9fed53cf89687cd1a5aa84c2d763c53af3fd72d7ce616fc"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "895M"
tar_bytes = 937473536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "199M"
zstd_bytes = 207981079

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "ruby_amd64_2022-03-28_11-12-rootfs.tar.zst"
previous_sha256 = "437dbc0c8f68923644b10aa9f533bf2ccec5e0793f1373559f22f97071dec79b"

current_version = "latest02"
current_date = "20220411"
old_file = "ruby_amd64_2022-03-24_12-37-rootfs.tar.zst"
old_sha256 = "2f91da052285b247f851564cffa93d149cb8e5b94628132e44c0ed7e387bfa87"
# edition 2021
# DISTRO_NAME=ruby_amd64
# ROOTFS_FILE=ruby_amd64_2022-04-11_11-16-rootfs.tar.zst
# SHA256SUM=0988899c205c7feeb9fed53cf89687cd1a5aa84c2d763c53af3fd72d7ce616fc
# BUILD_DATE=20220411
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest02
# END_TIME=11:16

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 11:02:39.994459094+00:00
start-sync_0 = 11:03:53
start-zstd = 11:05:17
start-sync_1 = 11:15:47
end-sync_1 = 11:16:07
end = 2022-04-11 11:16:07.424026118+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ruby = 'ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [x86_64-linux]'
gem = '3.3.7'
bundle = 'Bundler version 2.3.7'
```
