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
tag = ["latest", "2023-04-17", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-04-17_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f352172e60656f6a4085b3915065ff2cf3547e8dd9f48d16c7569356ca068926"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1605632000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "235M"
zstd_bytes = 246341328

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230414"
previous_tag = "2023-04-14"
previous_file = "rust_amd64_2023-04-14_03-00-rootfs.tar.zst"
previous_sha256 = "48867b1ad870500aa89d613830fda5d46619cade5623ace9596652611955f381"

current_version = "latest02"
current_date = "20230417"
old_file = "rust_amd64_2023-04-10_03-00-rootfs.tar.zst"
old_sha256 = "0d2d0ab2c75e85b201011d7743edbb6ad5bafe38e4b46cf69690a8d477988cac"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-04-17_03-00-rootfs.tar.zst
# SHA256SUM=f352172e60656f6a4085b3915065ff2cf3547e8dd9f48d16c7569356ca068926
# BUILD_DATE=20230417
# BUILD_TAG=2023-04-17
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-17
begin = 2023-04-17 02:52:31.599788327+00:00
start-sync_0 = 02:54:07
start-zstd = 02:55:08
start-sync_1 = 02:59:51
end-sync_1 = 03:00:17
end = 2023-04-17 03:00:17.018276800+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.71.0-nightly (d0a4cbcee 2023-04-16)'
rustc = 'rustc 1.71.0-nightly (d0f204e4d 2023-04-16)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.71.0-nightly (d0a4cbcee 2023-04-16)
release: 1.71.0-nightly
commit-hash: d0a4cbcee614fdb7ba66e860e603a00a644d71f8
commit-date: 2023-04-16
host: x86_64-unknown-linux-gnu
libgit2: 1.6.3 (sys:0.17.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Debian 12.0.0 [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (d0f204e4d 2023-04-16)
binary: rustc
commit-hash: d0f204e4d750b62f9d6c2593405e828757126832
commit-date: 2023-04-16
host: x86_64-unknown-linux-gnu
release: 1.71.0-nightly
LLVM version: 16.0.2
'''
```
