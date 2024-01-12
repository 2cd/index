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
tag = ["latest", "2024-01-12", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2024-01-12_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9a1563dd1760ad737e797a4c8d97f4e3102dfca36929db52f8eb17d76c16e6d3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1541301760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237187784

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_amd64_2023-11-27_02-59-rootfs.tar.zst"
previous_sha256 = "f45c11f16df406cf23cdeb613e3399d14f7688aa576ac5dee144d283c24b2989"

current_version = "latest01"
current_date = "20240112"
old_file = "rust_amd64_2023-11-24_02-58-rootfs.tar.zst"
old_sha256 = "f681d013a3aab174189f73ceb20c5e2fe1c5f5ad6b3b5941cc94e00a4ab1bc38"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2024-01-12_02-59-rootfs.tar.zst
# SHA256SUM=9a1563dd1760ad737e797a4c8d97f4e3102dfca36929db52f8eb17d76c16e6d3
# BUILD_DATE=20240112
# BUILD_TAG=2024-01-12
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-12
begin = 2024-01-12 02:52:33.395543037+00:00
start-sync_0 = 02:54:27
start-zstd = 02:55:12
start-sync_1 = 02:58:57
end-sync_1 = 02:59:15
end = 2024-01-12 02:59:15.924138780+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-13) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.77.0-nightly (3e428a38a 2024-01-09)'
rustc = 'rustc 1.77.0-nightly (62d7ed4a6 2024-01-11)'
cc = 'cc (Debian 13.2.0-9) 13.2.0'
cargo_verbose = '''
cargo 1.77.0-nightly (3e428a38a 2024-01-09)
release: 1.77.0-nightly
commit-hash: 3e428a38a34e820a461d2cc082e726d3bda71bcb
commit-date: 2024-01-09
host: x86_64-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.5.0-DEV (sys:0.4.70+curl-8.5.0 vendored ssl:OpenSSL/1.1.1w)
ssl: OpenSSL 1.1.1w  11 Sep 2023
os: Debian [64-bit]
'''
rustc_verbose = '''
rustc 1.77.0-nightly (62d7ed4a6 2024-01-11)
binary: rustc
commit-hash: 62d7ed4a6775c4490e493093ca98ef7c215b835b
commit-date: 2024-01-11
host: x86_64-unknown-linux-gnu
release: 1.77.0-nightly
LLVM version: 17.0.6
'''
```
