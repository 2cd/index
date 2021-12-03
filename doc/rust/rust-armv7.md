# rust-armv7

## How to run it?

```shell
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```shell
    docker exec -it rust-armv7 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-armv7 \
    cargo b --release
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2021-12-03_00-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d04ff50121854e8a03561fc587cd81a7efd431e3a5c00aac7ca33629137767fd"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "926M"
tar_bytes = 970654208

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237317269

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211129"
last_tag = "2021-11-29"
last_file = "rust_armhf_2021-11-29_00-40-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211203"
old_file = ""
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2021-12-03_00-12-rootfs.tar.zst
# BUILD_DATE=20211203
# BUILD_TAG=2021-12-03
# STATUS=completed
# VERSION=latest02
# END_TIME=00:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-03
begin = 2021-12-03 00:01:54.175098136+00:00
start-sync_0 = 00:07:20
start-zstd = 00:08:04
start-sync_1 = 00:11:43
end-sync_1 = 00:12:10
end = 2021-12-03 00:12:10.892352962+00:00

[server]
repo = "cake233/rust-armv7"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "us"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "global"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.58.0-nightly (294967c53 2021-11-29)'
rustc = 'rustc 1.59.0-nightly (48a5999fc 2021-12-01)'
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''
cargo 1.58.0-nightly (294967c53 2021-11-29)
release: 1.58.0
commit-hash: 294967c53f0c70d598fc54ca189313c86c576ea7
commit-date: 2021-11-29
host: armv7-unknown-linux-gnueabihf
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (48a5999fc 2021-12-01)
binary: rustc
commit-hash: 48a5999fceeea84a8971634355287faa349909d4
commit-date: 2021-12-01
host: armv7-unknown-linux-gnueabihf
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
