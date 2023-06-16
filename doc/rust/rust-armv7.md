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
tag = ["latest", "2023-06-16", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-06-16_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5356d3f30179437800e3de63ca73278c96e14e2f8fbf4330563400a1f6f9878a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1519637504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 226661108

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230612"
previous_tag = "2023-06-12"
previous_file = "rust_armhf_2023-06-12_03-04-rootfs.tar.zst"
previous_sha256 = "b0f499c8d44b5c32c5075491636b0e7e347630154f38e0e020473d5b381c08cb"

current_version = "latest02"
current_date = "20230616"
old_file = "rust_armhf_2023-06-09_03-04-rootfs.tar.zst"
old_sha256 = "11306fb6bdb55ff48b453b37eea6960ee40cc1570debbf0860a71423a7fe97b8"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-06-16_03-04-rootfs.tar.zst
# SHA256SUM=5356d3f30179437800e3de63ca73278c96e14e2f8fbf4330563400a1f6f9878a
# BUILD_DATE=20230616
# BUILD_TAG=2023-06-16
# STATUS=completed
# VERSION=latest02
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-16
begin = 2023-06-16 02:52:33.204238630+00:00
start-sync_0 = 02:58:24
start-zstd = 02:59:19
start-sync_1 = 03:03:46
end-sync_1 = 03:04:04
end = 2023-06-16 03:04:04.710397671+00:00

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
cargo = 'cargo 1.72.0-nightly (0c14026aa 2023-06-14)'
rustc = 'rustc 1.72.0-nightly (114fb86ca 2023-06-15)'
cc = 'cc (Debian 12.3.0-3) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (0c14026aa 2023-06-14)
release: 1.72.0-nightly
commit-hash: 0c14026aa84ee2ec4c67460c0a18abc8519ca6b2
commit-date: 2023-06-14
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (114fb86ca 2023-06-15)
binary: rustc
commit-hash: 114fb86ca08cfa6a99087e0f0bc264d03590dc37
commit-date: 2023-06-15
host: armv7-unknown-linux-gnueabihf
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
