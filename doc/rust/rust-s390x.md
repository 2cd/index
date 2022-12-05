# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-12-05", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2022-12-05_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2d160ee624e6fd7aa6b2c9d386c0c37c0da57fa2cb3a24401c0d4a2d39fd486c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1775861248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239431041

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221202"
previous_tag = "2022-12-02"
previous_file = "rust_s390x_2022-12-02_03-06-rootfs.tar.zst"
previous_sha256 = "2203a102210ce3c8b4a06b471987d267fd367ac366e9ad0ba9d54815d2552a8a"

current_version = "latest02"
current_date = "20221205"
old_file = "rust_s390x_2022-11-28_03-06-rootfs.tar.zst"
old_sha256 = "7e4a7152cd545dcb589d84cf2af38ae792a71bfaae75290785437bc719bf9a22"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-12-05_03-08-rootfs.tar.zst
# SHA256SUM=2d160ee624e6fd7aa6b2c9d386c0c37c0da57fa2cb3a24401c0d4a2d39fd486c
# BUILD_DATE=20221205
# BUILD_TAG=2022-12-05
# STATUS=completed
# VERSION=latest02
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-05
begin = 2022-12-05 02:52:28.147475627+00:00
start-sync_0 = 02:59:10
start-zstd = 03:00:18
start-sync_1 = 03:08:28
end-sync_1 = 03:08:48
end = 2022-12-05 03:08:48.959258480+00:00

[server]
repo = "cake233/rust-s390x"

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (f6e737b1e 2022-12-02)'
rustc = 'rustc 1.67.0-nightly (53e4b9dd7 2022-12-04)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (f6e737b1e 2022-12-02)
release: 1.67.0-nightly
commit-hash: f6e737b1e3386adb89333bf06a01f68a91ac5306
commit-date: 2022-12-02
host: s390x-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (53e4b9dd7 2022-12-04)
binary: rustc
commit-hash: 53e4b9dd74c29cc9308b8d0f10facac70bb101a7
commit-date: 2022-12-04
host: s390x-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
