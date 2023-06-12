# rust-armv7

## How to run it?

```sh
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```sh
docker exec -it rust-armv7 bash
```
<!-- repo=cake233/rust-armv7 -->

## Example

### set env

```sh
_UID="$(id -u)" || _UID=0
_GID="$(id -g)" || _GID=0
```

### create a new project

If "tmp/hello" already exists in the current directory, it can be skipped.

```sh
mkdir -p tmp

docker run \
    -t \
    --rm \
    -u "$_UID":"$_GID" \
    -v "$PWD"/tmp:/app \
    -w /app \
    cake233/rust-armv7 \
    cargo new hello
```

### cargo build

```sh
docker run \
    -t \
    --rm \
    -u "$_UID":"$_GID" \
    -v "$PWD"/tmp/hello:/app \
    -w /app \
    cake233/rust-armv7 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-06-12", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-06-12_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b0f499c8d44b5c32c5075491636b0e7e347630154f38e0e020473d5b381c08cb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1601444864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226440803

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230609"
previous_tag = "2023-06-09"
previous_file = "rust_armhf_2023-06-09_03-04-rootfs.tar.zst"
previous_sha256 = "11306fb6bdb55ff48b453b37eea6960ee40cc1570debbf0860a71423a7fe97b8"

current_version = "latest01"
current_date = "20230612"
old_file = "rust_armhf_2023-06-05_03-04-rootfs.tar.zst"
old_sha256 = "866a3f550379d0795c45994cd4c03be8110a25463fa3577e95ba27da71f31ff3"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-06-12_03-04-rootfs.tar.zst
# SHA256SUM=b0f499c8d44b5c32c5075491636b0e7e347630154f38e0e020473d5b381c08cb
# BUILD_DATE=20230612
# BUILD_TAG=2023-06-12
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-12
begin = 2023-06-12 02:52:43.328182252+00:00
start-sync_0 = 02:58:28
start-zstd = 02:59:29
start-sync_1 = 03:03:53
end-sync_1 = 03:04:12
end = 2023-06-12 03:04:12.051480012+00:00

[server]
repo = "cake233/rust-armv7"

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
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (49b6d9e17 2023-06-09)'
rustc = 'rustc 1.72.0-nightly (37998ab50 2023-06-11)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.72.0-nightly (49b6d9e17 2023-06-09)
release: 1.72.0-nightly
commit-hash: 49b6d9e179a91cf7645142541c9563443f64bf2b
commit-date: 2023-06-09
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (37998ab50 2023-06-11)
binary: rustc
commit-hash: 37998ab508d5d9fa0d465d7b535dc673087dda8f
commit-date: 2023-06-11
host: armv7-unknown-linux-gnueabihf
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
