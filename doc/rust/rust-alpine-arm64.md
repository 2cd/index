# rust-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-arm64 bash
```
<!-- repo=cake233/rust-alpine-arm64 -->

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
    cake233/rust-alpine-arm64 \
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
    cake233/rust-alpine-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2023-05-08", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-05-08_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2c63c53a1a39d01a4c45027cfb4529bed8c60c2b92ab938f0067e2e572608408"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "850M"
tar_bytes = 890958336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "156M"
zstd_bytes = 163022724

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230505"
previous_tag = "2023-05-05"
previous_file = "rust-musl_arm64_2023-05-05_03-01-rootfs.tar.zst"
previous_sha256 = "2f555c819c10f330ae209d010a77dec80278c1dd1ea9d32ee572a264853ea071"

current_version = "latest01"
current_date = "20230508"
old_file = "rust-musl_arm64_2023-05-01_03-01-rootfs.tar.zst"
old_sha256 = "be3e144fb531f5fd288c4f50c58932185f7c021d5b410560be9cbc4bff0c1ec7"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-05-08_03-02-rootfs.tar.zst
# SHA256SUM=2c63c53a1a39d01a4c45027cfb4529bed8c60c2b92ab938f0067e2e572608408
# BUILD_DATE=20230508
# BUILD_TAG=2023-05-08
# STATUS=completed
# VERSION=latest01
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-08
begin = 2023-05-08 02:52:34.153331966+00:00
start-sync_0 = 02:55:30
start-zstd = 02:56:22
start-sync_1 = 03:01:49
end-sync_1 = 03:02:08
end = 2023-05-08 03:02:08.778682479+00:00

[server]
repo = "cake233/rust-alpine-arm64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (aarch64) Version 1.2.4'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.71.0-nightly (569b648b5 2023-05-05)'
rustc = 'rustc 1.71.0-nightly (c4190f2d3 2023-05-07)'
cc = 'cc (Alpine 12.2.1_git20220924-r10) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.71.0-nightly (569b648b5 2023-05-05)
release: 1.71.0-nightly
commit-hash: 569b648b5831ae8a515e90c80843a5287c3304ef
commit-date: 2023-05-05
host: aarch64-unknown-linux-musl
libgit2: 1.6.3 (sys:0.17.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (c4190f2d3 2023-05-07)
binary: rustc
commit-hash: c4190f2d3a46a59f435f7b42f58bc22b2f4d6917
commit-date: 2023-05-07
host: aarch64-unknown-linux-musl
release: 1.71.0-nightly
LLVM version: 16.0.2
'''
```
