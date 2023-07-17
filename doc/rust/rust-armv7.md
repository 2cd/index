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
tag = ["latest", "2023-07-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-07-17_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "01d5868bdf0a38461a63e9c6667cce829cf6e27a05bb631017b5ef3033d90cce"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1810225152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "311M"
zstd_bytes = 326058984

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230714"
previous_tag = "2023-07-14"
previous_file = "rust_armhf_2023-07-14_03-10-rootfs.tar.zst"
previous_sha256 = "d196f02ffe5d2c0ea9c6a273d549cc2b2b4435daa22ad6c19ca9039cbf3e20a6"

current_version = "latest01"
current_date = "20230717"
old_file = "rust_armhf_2023-07-10_03-03-rootfs.tar.zst"
old_sha256 = "3fa919913dba558e835904358a9ae3241d9509396980245df81f56d009ea5cd9"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-07-17_03-06-rootfs.tar.zst
# SHA256SUM=01d5868bdf0a38461a63e9c6667cce829cf6e27a05bb631017b5ef3033d90cce
# BUILD_DATE=20230717
# BUILD_TAG=2023-07-17
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-17
begin = 2023-07-17 02:52:34.160284271+00:00
start-sync_0 = 02:59:06
start-zstd = 03:00:04
start-sync_1 = 03:06:18
end-sync_1 = 03:06:43
end = 2023-07-17 03:06:43.480819871+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (694a57956 2023-07-11)'
rustc = 'rustc 1.73.0-nightly (0e8e857b1 2023-07-16)'
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
rustc 1.73.0-nightly (0e8e857b1 2023-07-16)
binary: rustc
commit-hash: 0e8e857b11f60a785aea24a84f280f6dad7a4d42
commit-date: 2023-07-16
host: armv7-unknown-linux-gnueabihf
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
