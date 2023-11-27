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
tag = ["latest", "2023-11-27", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-11-27_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f45c11f16df406cf23cdeb613e3399d14f7688aa576ac5dee144d283c24b2989"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1566976000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237159727

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "rust_amd64_2023-11-24_02-58-rootfs.tar.zst"
previous_sha256 = "f681d013a3aab174189f73ceb20c5e2fe1c5f5ad6b3b5941cc94e00a4ab1bc38"

current_version = "latest02"
current_date = "20231127"
old_file = "rust_amd64_2023-11-20_02-59-rootfs.tar.zst"
old_sha256 = "16cc2332f7abe89081c58a663789fa2d1ff31dabfbb866d33f7a4f9526fe1a27"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-11-27_02-59-rootfs.tar.zst
# SHA256SUM=f45c11f16df406cf23cdeb613e3399d14f7688aa576ac5dee144d283c24b2989
# BUILD_DATE=20231127
# BUILD_TAG=2023-11-27
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-27
begin = 2023-11-27 02:52:36.325477388+00:00
start-sync_0 = 02:54:03
start-zstd = 02:54:50
start-sync_1 = 02:58:55
end-sync_1 = 02:59:14
end = 2023-11-27 02:59:14.204155112+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.76.0-nightly (9b13310ca 2023-11-24)'
rustc = 'rustc 1.76.0-nightly (6cf088810 2023-11-26)'
cc = 'cc (Debian 13.2.0-7) 13.2.0'
cargo_verbose = '''
cargo 1.76.0-nightly (9b13310ca 2023-11-24)
release: 1.76.0-nightly
commit-hash: 9b13310ca596020a737aaa47daa4ed9ff8898a2f
commit-date: 2023-11-24
host: x86_64-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Debian [64-bit]
'''
rustc_verbose = '''
rustc 1.76.0-nightly (6cf088810 2023-11-26)
binary: rustc
commit-hash: 6cf088810f66fff15d05bf7135c5f5888b7c93b4
commit-date: 2023-11-26
host: x86_64-unknown-linux-gnu
release: 1.76.0-nightly
LLVM version: 17.0.5
'''
```
