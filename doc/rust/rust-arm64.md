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
tag = ["latest", "2022-05-16", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-05-16_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a9f064f540d195752438daf9ac7a223de3b7c7387cbf17cec265b4310c36e021"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1819317760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "255M"
zstd_bytes = 267249238

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220513"
previous_tag = "2022-05-13"
previous_file = "rust_arm64_2022-05-13_03-09-rootfs.tar.zst"
previous_sha256 = "ac67e1346976f6c2dad7e9da14bd6cb17c2f58976ba00f309e625c43727a2bb1"

current_version = "latest02"
current_date = "20220516"
old_file = "rust_arm64_2022-05-06_03-06-rootfs.tar.zst"
old_sha256 = "5347434064b5884ac28edd0bbee1b2ae200251016b3c1ff424681d233f18454f"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-05-16_03-04-rootfs.tar.zst
# SHA256SUM=a9f064f540d195752438daf9ac7a223de3b7c7387cbf17cec265b4310c36e021
# BUILD_DATE=20220516
# BUILD_TAG=2022-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-16
begin = 2022-05-16 02:52:31.462608959+00:00
start-sync_0 = 02:58:11
start-zstd = 02:59:17
start-sync_1 = 03:04:34
end-sync_1 = 03:04:55
end = 2022-05-16 03:04:55.868233477+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (3f052d8ee 2022-05-12)'
rustc = 'rustc 1.63.0-nightly (42e1761c7 2022-05-15)'
cc = 'cc (Debian 11.3.0-1) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (3f052d8ee 2022-05-12)
release: 1.63.0-nightly
commit-hash: 3f052d8eed98c6a24f8b332fb2e6e6249d12d8c1
commit-date: 2022-05-12
host: aarch64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (42e1761c7 2022-05-15)
binary: rustc
commit-hash: 42e1761c704f074b7b8c7ff8a7433acfd65d2ee9
commit-date: 2022-05-15
host: aarch64-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.4
'''
```
