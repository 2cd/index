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
tag = ["alpine", "2023-06-26", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-06-26_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "cb5c15d4bca22671b23e6a177042f14d535dd1d2d71e5f2daf47bab30590d8f7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "863M"
tar_bytes = 904553472

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "157M"
zstd_bytes = 164444413

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230623"
previous_tag = "2023-06-23"
previous_file = "rust-musl_arm64_2023-06-23_03-02-rootfs.tar.zst"
previous_sha256 = "2fa09bb6c3bb4cb3f50b2f778fc21e2ad1b644d2a5ac0040b89a6f322fce3bf3"

current_version = "latest01"
current_date = "20230626"
old_file = "rust-musl_arm64_2023-06-19_03-00-rootfs.tar.zst"
old_sha256 = "30fec3cfbdbb0a46eab199480f29f12b9e4bfa9df78d5c35de0d95deb4681abb"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-06-26_03-01-rootfs.tar.zst
# SHA256SUM=cb5c15d4bca22671b23e6a177042f14d535dd1d2d71e5f2daf47bab30590d8f7
# BUILD_DATE=20230626
# BUILD_TAG=2023-06-26
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-26
begin = 2023-06-26 02:52:46.537125660+00:00
start-sync_0 = 02:55:10
start-zstd = 02:56:01
start-sync_1 = 03:01:35
end-sync_1 = 03:01:54
end = 2023-06-26 03:01:54.160322793+00:00

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
cargo = 'cargo 1.72.0-nightly (03bc66b55 2023-06-23)'
rustc = 'rustc 1.72.0-nightly (f7ca9df69 2023-06-24)'
cc = 'cc (Alpine 13.1.1_git20230617) 13.1.1 20230617'
cargo_verbose = '''
cargo 1.72.0-nightly (03bc66b55 2023-06-23)
release: 1.72.0-nightly
commit-hash: 03bc66b55c290324bd46eb22e369c8fae1908f91
commit-date: 2023-06-23
host: aarch64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (f7ca9df69 2023-06-24)
binary: rustc
commit-hash: f7ca9df69549470541fbf542f87a03eb9ed024b6
commit-date: 2023-06-24
host: aarch64-unknown-linux-musl
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
