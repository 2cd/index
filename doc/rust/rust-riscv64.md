# rust-riscv64

## How to run it?

```sh
docker run \
    -it \
    --name rust-riscv64 \
    cake233/rust-riscv64
```

## How to exec shell?

```sh
docker exec -it rust-riscv64 bash
```
<!-- repo=cake233/rust-riscv64 -->

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
    cake233/rust-riscv64 \
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
    cake233/rust-riscv64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-riscv64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-01-10", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
x11_or_wayland = false

[file]
name = "rust_riscv64_2022-01-10_03-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0b7516415e78058593dab1e4b2958948e86aa49325c9a6f96c62c1f9b844c62f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "952M"
tar_bytes = 998093312

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "198M"
zstd_bytes = 206672850

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220107"
previous_tag = "2022-01-07"
previous_file = "rust_riscv64_2022-01-07_03-02-rootfs.tar.zst"
previous_sha256 = "fbbbfc4b3947617370d08a19593cd89086b8619d2a196317a07a888fbebc5c25"

current_version = "latest01"
current_date = "20220110"
old_file = "rust_riscv64_2022-01-03_03-03-rootfs.tar.zst"
old_sha256 = "6d5f9b0a2c8c11b3caefcf3e8f86130fb249f8151a44450cca36aba67da40016"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-01-10_03-04-rootfs.tar.zst
# SHA256SUM=0b7516415e78058593dab1e4b2958948e86aa49325c9a6f96c62c1f9b844c62f
# BUILD_DATE=20220110
# BUILD_TAG=2022-01-10
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-10
begin = 2022-01-10 02:52:35.837584548+00:00
start-sync_0 = 02:59:10
start-zstd = 02:59:57
start-sync_1 = 03:04:24
end-sync_1 = 03:04:45
end = 2022-01-10 03:04:45.768660230+00:00

[server]
repo = "cake233/rust-riscv64"

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
host: riscv64gc-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (092e1c9d2 2022-01-09)
binary: rustc
commit-hash: 092e1c9d23158d81be27bb6f71bdd0c6282478fb
commit-date: 2022-01-09
host: riscv64gc-unknown-linux-gnu
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
