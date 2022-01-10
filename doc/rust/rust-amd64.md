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
tag = ["latest", "2022-01-10", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust_amd64_2022-01-10_03-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "93ab1ee11759f616ede0b41a70890969e037fa25c1d8c63655ff8c430ec8a94f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1528642560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239131922

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220107"
previous_tag = "2022-01-07"
previous_file = "rust_amd64_2022-01-07_03-01-rootfs.tar.zst"
previous_sha256 = "3f23b3e0f1f2ca0469291ebb56983929008a631113c2adc22ef1e064664b3306"

current_version = "latest01"
current_date = "20220110"
old_file = "rust_amd64_2022-01-03_02-59-rootfs.tar.zst"
old_sha256 = "47623ed128131beb3adaeb4aa671094401cd6d08b727f3d0312ab2edc7115fcd"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-01-10_03-00-rootfs.tar.zst
# SHA256SUM=93ab1ee11759f616ede0b41a70890969e037fa25c1d8c63655ff8c430ec8a94f
# BUILD_DATE=20220110
# BUILD_TAG=2022-01-10
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-10
begin = 2022-01-10 02:52:23.690293402+00:00
start-sync_0 = 02:54:03
start-zstd = 02:55:00
start-sync_1 = 03:00:14
end-sync_1 = 03:00:35
end = 2022-01-10 03:00:35.697582122+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-2) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.60.0-nightly (358e79fe5 2022-01-04)'
rustc = 'rustc 1.60.0-nightly (092e1c9d2 2022-01-09)'
cc = 'cc (Debian 11.2.0-13) 11.2.0'
cargo_verbose = '''
cargo 1.60.0-nightly (358e79fe5 2022-01-04)
release: 1.60.0-nightly
commit-hash: 358e79fe56fe374649275ca7aebaafd57ade0e8d
commit-date: 2022-01-04
host: x86_64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (092e1c9d2 2022-01-09)
binary: rustc
commit-hash: 092e1c9d23158d81be27bb6f71bdd0c6282478fb
commit-date: 2022-01-09
host: x86_64-unknown-linux-gnu
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
