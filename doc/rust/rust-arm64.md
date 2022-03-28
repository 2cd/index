# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-03-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust_arm64_2022-03-28_02-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7f8df153532c6c6a4ac00ca80ac51d917294bd8a5f70278ead4dfb8d33c336e5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1767565824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "254M"
zstd_bytes = 266029905

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220325"
previous_tag = "2022-03-25"
previous_file = "rust_arm64_2022-03-25_03-08-rootfs.tar.zst"
previous_sha256 = "b8c98d4827b3be5490474904940b7510750dd7b5a644e99d62b848d7f3f0f72e"

current_version = "latest01"
current_date = "20220328"
old_file = "rust_arm64_2022-03-21_03-04-rootfs.tar.zst"
old_sha256 = "0bf4982a5464c4f9935a6d09d30b2302023d62eae600c881266d54c41d0d381a"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-03-28_02-08-rootfs.tar.zst
# SHA256SUM=7f8df153532c6c6a4ac00ca80ac51d917294bd8a5f70278ead4dfb8d33c336e5
# BUILD_DATE=20220328
# BUILD_TAG=2022-03-28
# STATUS=completed
# VERSION=latest01
# END_TIME=02:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-28
begin = 2022-03-28 01:52:27.870444042+00:00
start-sync_0 = 02:00:05
start-zstd = 02:01:18
start-sync_1 = 02:08:00
end-sync_1 = 02:08:23
end = 2022-03-28 02:08:23.433378773+00:00

[server]
repo = "cake233/rust-arm64"

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
cargo = 'cargo 1.61.0-nightly (109bfbd 2022-03-17)'
rustc = 'rustc 1.61.0-nightly (ab0c2e18d 2022-03-27)'
cc = 'cc (Debian 11.2.0-19) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (109bfbd 2022-03-17)
release: 1.61.0-nightly
commit-hash: 109bfbd055325ef87a6e7f63d67da7e838f8300b
commit-date: 2022-03-17
host: aarch64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (ab0c2e18d 2022-03-27)
binary: rustc
commit-hash: ab0c2e18dceb7140626a158affb983ae81039bd0
commit-date: 2022-03-27
host: aarch64-unknown-linux-gnu
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
