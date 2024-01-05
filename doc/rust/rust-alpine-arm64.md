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
tag = ["alpine", "2024-01-05", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2024-01-05_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "38dbc3acced56de5558fc3a743bfaafd0ea1d71721f5ffef02ae3451cc5ec7d2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "866M"
tar_bytes = 907985920

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "160M"
zstd_bytes = 167301733

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust-musl_arm64_2023-11-27_02-59-rootfs.tar.zst"
previous_sha256 = "b51e722856c8ad7a2f143ccc282458cab9f0dd59d725d9f9c1506674259cb1f3"

current_version = "latest02"
current_date = "20240105"
old_file = "rust-musl_arm64_2023-11-24_02-59-rootfs.tar.zst"
old_sha256 = "d825e1766df34ed19d77d5151cf86314e7904feacd1786d6242976d234d0db15"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2024-01-05_02-59-rootfs.tar.zst
# SHA256SUM=38dbc3acced56de5558fc3a743bfaafd0ea1d71721f5ffef02ae3451cc5ec7d2
# BUILD_DATE=20240105
# BUILD_TAG=2024-01-05
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-05
begin = 2024-01-05 02:52:31.826389004+00:00
start-sync_0 = 02:54:28
start-zstd = 02:54:58
start-sync_1 = 02:59:24
end-sync_1 = 02:59:35
end = 2024-01-05 02:59:35.799907225+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.77.0-nightly (add15366e 2024-01-02)'
rustc = 'rustc 1.77.0-nightly (f688dd684 2024-01-04)'
cc = 'cc (Alpine 13.2.1_git20231014) 13.2.1 20231014'
cargo_verbose = '''
cargo 1.77.0-nightly (add15366e 2024-01-02)
release: 1.77.0-nightly
commit-hash: add15366eaf3f3eb84717d3b8b71902ca36a7c84
commit-date: 2024-01-02
host: aarch64-unknown-linux-musl
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.5.0-DEV (sys:0.4.70+curl-8.5.0 vendored ssl:OpenSSL/1.1.1w)
ssl: OpenSSL 1.1.1w  11 Sep 2023
os: Alpine Linux 3.20.0_alpha20231219 [64-bit]
'''
rustc_verbose = '''
rustc 1.77.0-nightly (f688dd684 2024-01-04)
binary: rustc
commit-hash: f688dd684faca5b31b156fac2c6e0ae81fc9bc90
commit-date: 2024-01-04
host: aarch64-unknown-linux-musl
release: 1.77.0-nightly
LLVM version: 17.0.6
'''
```
