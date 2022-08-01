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
tag = ["latest", "2022-08-01", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-08-01_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5dfaab7e598c1149bc1296fc85be86fa8994aa5ab329e4074403dd5e87f47f5b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1727820288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239716532

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_riscv64_2022-07-18_03-05-rootfs.tar.zst"
previous_sha256 = "fa4633c476191045034bb14f252e552441ecb4d2558009893db749c3da9c9814"

current_version = "latest01"
current_date = "20220801"
old_file = "rust_riscv64_2022-07-15_03-05-rootfs.tar.zst"
old_sha256 = "c279944c63b02260d5a390be7a494aae599c0894598aac7ef18cc0e2471c4862"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-08-01_03-05-rootfs.tar.zst
# SHA256SUM=5dfaab7e598c1149bc1296fc85be86fa8994aa5ab329e4074403dd5e87f47f5b
# BUILD_DATE=20220801
# BUILD_TAG=2022-08-01
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-01
begin = 2022-08-01 02:52:29.456226142+00:00
start-sync_0 = 02:58:50
start-zstd = 02:59:51
start-sync_1 = 03:05:36
end-sync_1 = 03:05:55
end = 2022-08-01 03:05:55.371064675+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (85b500cca 2022-07-24)'
rustc = 'rustc 1.64.0-nightly (f9cba6374 2022-07-31)'
cc = 'cc (Debian 12.1.0-7) 12.1.0'
cargo_verbose = '''
cargo 1.64.0-nightly (85b500cca 2022-07-24)
release: 1.64.0-nightly
commit-hash: 85b500ccad8cd0b63995fd94a03ddd4b83f7905b
commit-date: 2022-07-24
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (f9cba6374 2022-07-31)
binary: rustc
commit-hash: f9cba63746d0fff816250b2ba7b706b5d4dcf000
commit-date: 2022-07-31
host: riscv64gc-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
