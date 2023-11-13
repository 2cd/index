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
tag = ["latest", "2023-11-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-11-13_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ee30db6666d520aaca6f0e125f629742eda7540f3615fef7cf3195d5e140116c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1581754880

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "221M"
zstd_bytes = 231475992

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231110"
previous_tag = "2023-11-10"
previous_file = "rust_armhf_2023-11-10_03-04-rootfs.tar.zst"
previous_sha256 = "0696aebc4a92b35ebee1d14983434d30abeb3c5e01d8457a0112d0b98cad805c"

current_version = "latest01"
current_date = "20231113"
old_file = "rust_armhf_2023-10-27_03-09-rootfs.tar.zst"
old_sha256 = "0c2f5b0d5108618156e4f7a9ffce1dfc260e0d1935461ddef7d9af155c8442fb"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-11-13_03-02-rootfs.tar.zst
# SHA256SUM=ee30db6666d520aaca6f0e125f629742eda7540f3615fef7cf3195d5e140116c
# BUILD_DATE=20231113
# BUILD_TAG=2023-11-13
# STATUS=completed
# VERSION=latest01
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-13
begin = 2023-11-13 02:52:29.292847331+00:00
start-sync_0 = 02:57:16
start-zstd = 02:58:01
start-sync_1 = 03:02:02
end-sync_1 = 03:02:16
end = 2023-11-13 03:02:16.566501946+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.76.0-nightly (6790a5127 2023-11-10)'
rustc = 'rustc 1.76.0-nightly (2b603f95a 2023-11-12)'
cc = 'cc (Debian 13.2.0-6) 13.2.0'
cargo_verbose = '''
cargo 1.76.0-nightly (6790a5127 2023-11-10)
release: 1.76.0-nightly
commit-hash: 6790a5127895debec95c24aefaeb18e059270df3
commit-date: 2023-11-10
host: armv7-unknown-linux-gnueabihf
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.76.0-nightly (2b603f95a 2023-11-12)
binary: rustc
commit-hash: 2b603f95a48f10f931a61dd208fe3e5ffd64e491
commit-date: 2023-11-12
host: armv7-unknown-linux-gnueabihf
release: 1.76.0-nightly
LLVM version: 17.0.4
'''
```
