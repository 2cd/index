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
tag = ["latest", "2023-02-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-02-17_10-37.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d7d9aa06943655ab4f72d5fac429e08f0c7fb8e329dfba45d904c803167c94e8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1542316544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "215M"
zstd_bytes = 225307372

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230217"
previous_tag = "2023-02-17"
previous_file = "rust_armhf_2023-02-17_03-03-rootfs.tar.zst"
previous_sha256 = "8475051169e5720d3477b539c23725f658db9aea937497c654e45c3cbccb5e72"

current_version = "latest02"
current_date = "20230217"
old_file = "rust_armhf_2023-02-10_03-03-rootfs.tar.zst"
old_sha256 = "9403248602fb30400788786cb76a7515999993200104f3c1d2c3e36a624775b8"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-02-17_10-37-rootfs.tar.zst
# SHA256SUM=d7d9aa06943655ab4f72d5fac429e08f0c7fb8e329dfba45d904c803167c94e8
# BUILD_DATE=20230217
# BUILD_TAG=2023-02-17
# STATUS=completed
# VERSION=latest02
# END_TIME=10:37

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-17
begin = 2023-02-17 10:25:47.615853136+00:00
start-sync_0 = 10:31:42
start-zstd = 10:32:43
start-sync_1 = 10:36:59
end-sync_1 = 10:37:18
end = 2023-02-17 10:37:18.106296961+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.69.0-nightly (39c13e67a 2023-02-12)'
rustc = 'rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (39c13e67a 2023-02-12)
release: 1.69.0-nightly
commit-hash: 39c13e67a5962466cc7253d41bc1099bbcb224c3
commit-date: 2023-02-12
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (9a7cc6c32 2023-02-16)
binary: rustc
commit-hash: 9a7cc6c32f1a690f86827e4724bcda85e506ef35
commit-date: 2023-02-16
host: armv7-unknown-linux-gnueabihf
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
