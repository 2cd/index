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
tag = ["latest", "2023-06-26", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-06-26_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1e97dc87b6994e8489569155897705139673b9c949a9792b93586f9c1acd73be"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1867530752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "245M"
zstd_bytes = 256644734

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230623"
previous_tag = "2023-06-23"
previous_file = "rust_arm64_2023-06-23_03-06-rootfs.tar.zst"
previous_sha256 = "389da9f7881ee226c4b8b1edec7dc536ca11f32edc86f95558b8d501876815b1"

current_version = "latest02"
current_date = "20230626"
old_file = "rust_arm64_2023-06-16_03-08-rootfs.tar.zst"
old_sha256 = "c32f43158c50db3fbfab50178c2231258c44da4ff6a235abdab6093230957e3f"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-06-26_03-06-rootfs.tar.zst
# SHA256SUM=1e97dc87b6994e8489569155897705139673b9c949a9792b93586f9c1acd73be
# BUILD_DATE=20230626
# BUILD_TAG=2023-06-26
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-26
begin = 2023-06-26 02:52:35.985033288+00:00
start-sync_0 = 02:58:31
start-zstd = 02:59:36
start-sync_1 = 03:05:48
end-sync_1 = 03:06:10
end = 2023-06-26 03:06:10.180727803+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (03bc66b55 2023-06-23)'
rustc = 'rustc 1.72.0-nightly (f7ca9df69 2023-06-24)'
cc = 'cc (Debian 12.3.0-4) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (03bc66b55 2023-06-23)
release: 1.72.0-nightly
commit-hash: 03bc66b55c290324bd46eb22e369c8fae1908f91
commit-date: 2023-06-23
host: aarch64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (f7ca9df69 2023-06-24)
binary: rustc
commit-hash: f7ca9df69549470541fbf542f87a03eb9ed024b6
commit-date: 2023-06-24
host: aarch64-unknown-linux-gnu
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
