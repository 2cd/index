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
tag = ["latest", "2021-12-31", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust_arm64_2021-12-31_03-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "cb980becc215a55a7309e652176b1b157ade6ffb6f22638ae3f5ea0375073e25"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1771857408

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "263M"
zstd_bytes = 275491860

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211227"
previous_tag = "2021-12-27"
previous_file = "rust_arm64_2021-12-27_03-04-rootfs.tar.zst"
previous_sha256 = "7c108a42a6b0952e86329f1ed6fb85c0644efdd826bbdb4a71d87926fa952f1d"

current_version = "latest01"
current_date = "20211231"
old_file = "rust_arm64_2021-12-24_03-06-rootfs.tar.zst"
old_sha256 = "811340af8f0510c736c118da08e9e9a284957df450009a66160e7c8d0af94c63"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2021-12-31_03-06-rootfs.tar.zst
# SHA256SUM=cb980becc215a55a7309e652176b1b157ade6ffb6f22638ae3f5ea0375073e25
# BUILD_DATE=20211231
# BUILD_TAG=2021-12-31
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-31
begin = 2021-12-31 02:52:21.971410278+00:00
start-sync_0 = 02:59:19
start-zstd = 03:00:32
start-sync_1 = 03:06:33
end-sync_1 = 03:06:56
end = 2021-12-31 03:06:56.656883564+00:00

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
host: aarch64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (b60e32c82 2021-12-30)
binary: rustc
commit-hash: b60e32c82864d841e87359333af1e6d1f9cff9ee
commit-date: 2021-12-30
host: aarch64-unknown-linux-gnu
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
