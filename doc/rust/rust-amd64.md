# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-12-31", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust_amd64_2021-12-31_03-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "28753e85b4cd34c3cd97b7e8a512996fa7ac0ff9c51fd08d9f6f93968d5da340"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1533839872

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239658065

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211227"
previous_tag = "2021-12-27"
previous_file = "rust_amd64_2021-12-27_03-01-rootfs.tar.zst"
previous_sha256 = "52848184c4bf3d9fea728f66f79340e984d7ff27e320ed1cb438d244c84e8ee9"

current_version = "latest02"
current_date = "20211231"
old_file = "rust_amd64_2021-12-24_03-00-rootfs.tar.zst"
old_sha256 = "78cc420f9b2d4b0d2c1d60e0cf16234ac2b9fd10a044802d79b7420f25364cd1"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2021-12-31_03-00-rootfs.tar.zst
# SHA256SUM=28753e85b4cd34c3cd97b7e8a512996fa7ac0ff9c51fd08d9f6f93968d5da340
# BUILD_DATE=20211231
# BUILD_TAG=2021-12-31
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-31
begin = 2021-12-31 02:52:23.638597030+00:00
start-sync_0 = 02:54:15
start-zstd = 02:55:18
start-sync_1 = 03:00:39
end-sync_1 = 03:00:59
end = 2021-12-31 03:00:59.956680476+00:00

[server]
repo = "cake233/rust-amd64"

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
ldd = 'ldd (Debian GLIBC 2.33-1) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.59.0-nightly (fcef61230 2021-12-17)'
rustc = 'rustc 1.59.0-nightly (b60e32c82 2021-12-30)'
cc = 'cc (Debian 11.2.0-13) 11.2.0'
cargo_verbose = '''
cargo 1.59.0-nightly (fcef61230 2021-12-17)
release: 1.59.0-nightly
commit-hash: fcef61230c3b6213b6b0d233a36ba4ebd1649ec3
commit-date: 2021-12-17
host: x86_64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (b60e32c82 2021-12-30)
binary: rustc
commit-hash: b60e32c82864d841e87359333af1e6d1f9cff9ee
commit-date: 2021-12-30
host: x86_64-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
