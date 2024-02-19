# ruby-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name ruby-alpine-arm64 \
    cake233/ruby-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it ruby-alpine-arm64 bash
```

## ruby-alpine-arm64.toml

```toml
[main]
name = "ruby"
tag = ["alpine", "2024-02-19", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "ruby-musl_arm64_2024-02-19_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d928afc79d3bc62133c1d7a723b1a351bf04f5120bc1fbbf2beaea60ba892650"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "109M"
tar_bytes = 113488896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "41M"
zstd_bytes = 42475276

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231120"
previous_tag = "2023-11-20"
previous_file = "ruby-musl_arm64_2023-11-20_12-05-rootfs.tar.zst"
previous_sha256 = "b17e54a2d369c4477ae6b85c5b47c2fdc214bd4086bed353570a226b87b8b490"

current_version = "latest01"
current_date = "20240219"
old_file = "ruby-musl_arm64_2023-10-23_12-05-rootfs.tar.zst"
old_sha256 = "adb94669c9065d82adf47bec9ade80cc7974c323c6ed38478c9db89beb17e0e0"
# edition 2021
# DISTRO_NAME=ruby_arm64
# ROOTFS_FILE=ruby-musl_arm64_2024-02-19_12-06-rootfs.tar.zst
# SHA256SUM=d928afc79d3bc62133c1d7a723b1a351bf04f5120bc1fbbf2beaea60ba892650
# BUILD_DATE=20240219
# BUILD_TAG=2024-02-19
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-19
begin = 2024-02-19 12:02:37.589412041+00:00
start-sync_0 = 12:05:05
start-zstd = 12:05:13
start-sync_1 = 12:05:55
end-sync_1 = 12:06:03
end = 2024-02-19 12:06:03.828978464+00:00

[server]
repo = "cake233/ruby-alpine-arm64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/bundle/bin${PATH:+:${PATH}}"
GEM_HOME = '/usr/local/bundle'
BUNDLE_SILENCE_ROOT_WARNING = '1'
BUNDLE_APP_CONFIG = '/usr/local/bundle'

[version]
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
ruby = 'ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [aarch64-linux-musl]'
gem = '3.5.3'
bundle = 'Bundler version 2.5.3'
```
