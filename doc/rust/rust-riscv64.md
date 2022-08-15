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
tag = ["latest", "2022-08-15", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-08-15_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d1b99aeb0ab1d8a6169dd7df8fb974d0117dc8e2afd3ca2b2c153fc2eeb26a7b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1630118400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "223M"
zstd_bytes = 233065913

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220812"
previous_tag = "2022-08-12"
previous_file = "rust_riscv64_2022-08-12_03-05-rootfs.tar.zst"
previous_sha256 = "e45a1f93baa02f95679ffe0b45c5cb81890514e68585ad4c002c8ad2652194b5"

current_version = "latest02"
current_date = "20220815"
old_file = "rust_riscv64_2022-08-08_03-04-rootfs.tar.zst"
old_sha256 = "247ca2bd06947c3970165ab86fdedc84f5c1e9c7326702c70cc53a91edae0970"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-08-15_03-05-rootfs.tar.zst
# SHA256SUM=d1b99aeb0ab1d8a6169dd7df8fb974d0117dc8e2afd3ca2b2c153fc2eeb26a7b
# BUILD_DATE=20220815
# BUILD_TAG=2022-08-15
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-15
begin = 2022-08-15 02:52:22.988656070+00:00
start-sync_0 = 02:59:21
start-zstd = 03:00:20
start-sync_1 = 03:05:25
end-sync_1 = 03:05:49
end = 2022-08-15 03:05:49.915790277+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-3) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (efd4ca3dc 2022-08-12)'
rustc = 'rustc 1.65.0-nightly (801821d15 2022-08-14)'
cc = 'cc (Debian 12.1.0-8) 12.1.0'
cargo_verbose = '''
cargo 1.65.0-nightly (efd4ca3dc 2022-08-12)
release: 1.65.0-nightly
commit-hash: efd4ca3dc0b89929dc8c5f5c023d25978d76cb61
commit-date: 2022-08-12
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (801821d15 2022-08-14)
binary: rustc
commit-hash: 801821d1560f84e4716fcbd9244ec959320a13d5
commit-date: 2022-08-14
host: riscv64gc-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
