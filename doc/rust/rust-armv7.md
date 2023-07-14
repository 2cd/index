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
tag = ["latest", "2023-07-14", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-07-14_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d196f02ffe5d2c0ea9c6a273d549cc2b2b4435daa22ad6c19ca9039cbf3e20a6"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1811298304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "312M"
zstd_bytes = 326232891

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230710"
previous_tag = "2023-07-10"
previous_file = "rust_armhf_2023-07-10_03-03-rootfs.tar.zst"
previous_sha256 = "3fa919913dba558e835904358a9ae3241d9509396980245df81f56d009ea5cd9"

current_version = "latest02"
current_date = "20230714"
old_file = "rust_armhf_2023-07-07_03-04-rootfs.tar.zst"
old_sha256 = "990d54be7ba06d67e2979aa2563e4e8c5c91434fe6d1a3245c460f3726cd9d25"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-07-14_03-10-rootfs.tar.zst
# SHA256SUM=d196f02ffe5d2c0ea9c6a273d549cc2b2b4435daa22ad6c19ca9039cbf3e20a6
# BUILD_DATE=20230714
# BUILD_TAG=2023-07-14
# STATUS=completed
# VERSION=latest02
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-14
begin = 2023-07-14 02:52:40.567244952+00:00
start-sync_0 = 03:01:17
start-zstd = 03:02:34
start-sync_1 = 03:09:40
end-sync_1 = 03:10:10
end = 2023-07-14 03:10:10.815074578+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-5) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (694a57956 2023-07-11)'
rustc = 'rustc 1.73.0-nightly (7bd81ee19 2023-07-13)'
cc = 'cc (Debian 13.1.0-8) 13.1.0'
cargo_verbose = '''
cargo 1.73.0-nightly (694a57956 2023-07-11)
release: 1.73.0-nightly
commit-hash: 694a579566a9a1482b20aff8a68f0e4edd99bd28
commit-date: 2023-07-11
host: armv7-unknown-linux-gnueabihf
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (7bd81ee19 2023-07-13)
binary: rustc
commit-hash: 7bd81ee1902c049691d0a1f03be5558bee51d100
commit-date: 2023-07-13
host: armv7-unknown-linux-gnueabihf
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
