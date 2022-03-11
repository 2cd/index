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
tag = ["latest", "2022-03-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2022-03-11_03-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "22a36996f7bbe199102ee4a17d21dba0c23af72bdc92cb75b9c26cd2b2398a65"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1507426304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "231M"
zstd_bytes = 241527749

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "rust_armhf_2022-03-07_03-03-rootfs.tar.zst"
previous_sha256 = "7e765dff6cebe270cced5d8341f4cdff13166e2ed4231a9b7e07b2ff9815721a"

current_version = "latest01"
current_date = "20220311"
old_file = "rust_armhf_2022-03-04_03-05-rootfs.tar.zst"
old_sha256 = "3b68339f483cc235fa1a0b05ceeeefaf8587653b03b47aed22a140b16c8090c4"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-03-11_03-06-rootfs.tar.zst
# SHA256SUM=22a36996f7bbe199102ee4a17d21dba0c23af72bdc92cb75b9c26cd2b2398a65
# BUILD_DATE=20220311
# BUILD_TAG=2022-03-11
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-11
begin = 2022-03-11 02:52:26.139275170+00:00
start-sync_0 = 02:59:50
start-zstd = 03:00:51
start-sync_1 = 03:05:51
end-sync_1 = 03:06:16
end = 2022-03-11 03:06:16.632470939+00:00

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
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (65c826642 2022-03-09)'
rustc = 'rustc 1.61.0-nightly (5f4e06771 2022-03-10)'
cc = 'cc (Debian 11.2.0-18) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (65c826642 2022-03-09)
release: 1.61.0-nightly
commit-hash: 65c82664263feddc5fe2d424be0993c28d46377a
commit-date: 2022-03-09
host: armv7-unknown-linux-gnueabihf
libgit2: 1.4.1 (sys:0.14.1 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (5f4e06771 2022-03-10)
binary: rustc
commit-hash: 5f4e0677190b82e61dc507e3e72caf89da8e5e28
commit-date: 2022-03-10
host: armv7-unknown-linux-gnueabihf
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
