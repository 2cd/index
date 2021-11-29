# rust-arm64

## How to run it?

```shell
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```shell
    docker exec -it rust-arm64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-arm64 \
    cargo b --release
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-11-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust_arm64_2021-11-29_00-44.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "1523c9bf8c9a2a1628a4e5d56c9ff8a0999d0435c731f4c2aa3b8b2f8e4111b7"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1766415360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "263M"
zstd_bytes = 275177467

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211101"
last_tag = ""
last_file = "rust_arm64+latest-2021_11-01-rootfs.tar.zst"

current_version = "latest02"
current_date = "20211129"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2021-11-29_00-44.tar.zst
# BUILD_DATE=20211129
# BUILD_TAG=2021-11-29
# STATUS=completed
# VERSION=latest02
# END_TIME=00:44

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-29
begin = 2021-11-29 00:27:08.581464833+00:00
start-sync_0 = 00:35:57
start-zstd = 00:37:25
start-sync_1 = 00:44:07
end-sync_1 = 00:44:35
end = 2021-11-29 00:44:36.001497429+00:00

[server]
repo = "cake233/rust-arm64"

[server.node1]
name = "cn"
current = false
last = true
split = false

[server.node2]
name = "us"
current = false
last = true
split = false
part = 12

[server.node3]
name = "global"
current = false
last = true
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
cargo = 'cargo 1.58.0-nightly (7f08ace4f 2021-11-24)'
rustc = 'rustc 1.59.0-nightly (686e313a9 2021-11-27)'
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''
cargo 1.58.0-nightly (7f08ace4f 2021-11-24)
release: 1.58.0
commit-hash: 7f08ace4f1305de7f3b1b0e2f765911957226bd4
commit-date: 2021-11-24
host: aarch64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (686e313a9 2021-11-27)
binary: rustc
commit-hash: 686e313a9aa14107c8631ffe48fa09110a7692db
commit-date: 2021-11-27
host: aarch64-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
