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
tag = ["latest", "2023-08-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-08-25_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "792e3c75e98c5458a1b123b02d45679c84bda9fa06347d858a73283040cac6fa"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1569897472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 227821607

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230821"
previous_tag = "2023-08-21"
previous_file = "rust_amd64_2023-08-21_03-00-rootfs.tar.zst"
previous_sha256 = "9496711d8c439539f4edd02b25405deb32cb19ed6b48b97ca4d2c8bac54cfb0d"

current_version = "latest02"
current_date = "20230825"
old_file = "rust_amd64_2023-08-18_02-59-rootfs.tar.zst"
old_sha256 = "b442f700c27b7cb8c5cb20a5ed8e73f80674bdc38216b7dccc99b278d87887e9"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-08-25_03-02-rootfs.tar.zst
# SHA256SUM=792e3c75e98c5458a1b123b02d45679c84bda9fa06347d858a73283040cac6fa
# BUILD_DATE=20230825
# BUILD_TAG=2023-08-25
# STATUS=completed
# VERSION=latest02
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-25
begin = 2023-08-25 02:52:34.256707037+00:00
start-sync_0 = 02:54:43
start-zstd = 02:55:48
start-sync_1 = 03:01:37
end-sync_1 = 03:02:02
end = 2023-08-25 03:02:02.096275815+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (2cc50bc0b 2023-08-22)'
rustc = 'rustc 1.74.0-nightly (58eefc33a 2023-08-24)'
cc = 'cc (Debian 13.2.0-2) 13.2.0'
cargo_verbose = '''
cargo 1.74.0-nightly (2cc50bc0b 2023-08-22)
release: 1.74.0-nightly
commit-hash: 2cc50bc0b63ad20da193e002ba11d391af0104b7
commit-date: 2023-08-22
host: x86_64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Debian [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (58eefc33a 2023-08-24)
binary: rustc
commit-hash: 58eefc33adf769a1abe12ad94b3e6811185b4ce5
commit-date: 2023-08-24
host: x86_64-unknown-linux-gnu
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
