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
tag = ["latest", "2022-03-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2022-03-25_03-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "b0969040d53c2326cc3b316f7e6483911854752e3f5913a6ac422d97ba8de7c3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1516253184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "233M"
zstd_bytes = 243597790

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220321"
previous_tag = "2022-03-21"
previous_file = "rust_armhf_2022-03-21_03-05-rootfs.tar.zst"
previous_sha256 = "eb4606256e7ecb4f81187fb9b663d60b56d93fd1d711113aa949ef6ab3b63b0a"

current_version = "latest01"
current_date = "20220325"
old_file = "rust_armhf_2022-03-18_03-03-rootfs.tar.zst"
old_sha256 = "f748a39f396046608b5070ab7c4a428379b8c96e231b25ed7a653c4f46ac0925"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-03-25_03-04-rootfs.tar.zst
# SHA256SUM=b0969040d53c2326cc3b316f7e6483911854752e3f5913a6ac422d97ba8de7c3
# BUILD_DATE=20220325
# BUILD_TAG=2022-03-25
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-25
begin = 2022-03-25 02:52:26.585830196+00:00
start-sync_0 = 02:58:29
start-zstd = 02:59:23
start-sync_1 = 03:04:02
end-sync_1 = 03:04:21
end = 2022-03-25 03:04:21.337156222+00:00

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
cargo = 'cargo 1.61.0-nightly (109bfbd05 2022-03-17)'
rustc = 'rustc 1.61.0-nightly (63b8f01bb 2022-03-24)'
cc = 'cc (Debian 11.2.0-18) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (109bfbd05 2022-03-17)
release: 1.61.0-nightly
commit-hash: 109bfbd055325ef87a6e7f63d67da7e838f8300b
commit-date: 2022-03-17
host: armv7-unknown-linux-gnueabihf
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (63b8f01bb 2022-03-24)
binary: rustc
commit-hash: 63b8f01bb5ca277e7df8d7efe094ed4244c1790c
commit-date: 2022-03-24
host: armv7-unknown-linux-gnueabihf
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
