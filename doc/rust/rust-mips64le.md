# rust-mips64le

## How to run it?

```shell
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```shell
    docker exec -it rust-mips64le bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    cake233/rust-mips64le \
    cargo b --release
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
x11_or_wayland = false

[file]
name = "rust_mips64el_2021-12-06_10-40.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "347526a529df76fa999b6cb93f104b4fe889fee5aad3d82da728dc04a47b20b9"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1018M"
tar_bytes = 1067191808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "202M"
zstd_bytes = 211650415

[compatibility]
compatible_mode = true

last_version = "latest02"

# The value is &str, not int
last_date = "20211203"
last_tag = "2021-12-03"
last_file = "rust_mips64el_2021-12-03_00-13-rootfs.tar.zst"

current_version = "latest01"
current_date = "20211206"
old_file = "rust_mips64el_2021-11-29_00-41-rootfs.tar.zst"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2021-12-06_10-40-rootfs.tar.zst
# BUILD_DATE=20211206
# BUILD_TAG=2021-12-06
# STATUS=completed
# VERSION=latest01
# END_TIME=10:40

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-06
begin = 2021-12-06 10:28:29.973267178+00:00
start-sync_0 = 10:34:55
start-zstd = 10:35:42
start-sync_1 = 10:40:20
end-sync_1 = 10:40:39
end = 2021-12-06 10:40:39.781685878+00:00

[server]
repo = "cake233/rust-mips64le"

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
rustc = 'rustc 1.59.0-nightly (e2116acae 2021-12-05)'
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''
cargo 1.58.0-nightly (294967c53 2021-11-29)
release: 1.58.0
commit-hash: 294967c53f0c70d598fc54ca189313c86c576ea7
commit-date: 2021-11-29
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (e2116acae 2021-12-05)
binary: rustc
commit-hash: e2116acae59654bfab2a9729a024f3e2fd6d4b02
commit-date: 2021-12-05
host: mips64el-unknown-linux-gnuabi64
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
