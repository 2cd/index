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
tag = ["alpine", "2022-09-09", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-09-09_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4e85ce16dfee53d034b19e673c71d05a9c214ac634f160000ae6865728da1f68"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "776M"
tar_bytes = 812769280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "151M"
zstd_bytes = 157686901

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220905"
previous_tag = "2022-09-05"
previous_file = "rust-musl_arm64_2022-09-05_03-01-rootfs.tar.zst"
previous_sha256 = "0aa6f860d0dbe06216285397c011c2d46594758ba2f08cd300c02e005bcffccf"

current_version = "latest01"
current_date = "20220909"
old_file = "rust-musl_arm64_2022-09-02_03-00-rootfs.tar.zst"
old_sha256 = "b3587af373427d0fc6d96ad1a28443bb123a47f7623562862cde9acc0298d638"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-09-09_03-01-rootfs.tar.zst
# SHA256SUM=4e85ce16dfee53d034b19e673c71d05a9c214ac634f160000ae6865728da1f68
# BUILD_DATE=20220909
# BUILD_TAG=2022-09-09
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-09
begin = 2022-09-09 02:52:26.107842513+00:00
start-sync_0 = 02:54:44
start-zstd = 02:55:31
start-sync_1 = 03:00:53
end-sync_1 = 03:01:10
end = 2022-09-09 03:01:10.245516182+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.3'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (646e9a0b9 2022-09-02)'
rustc = 'rustc 1.65.0-nightly (1120c5e01 2022-09-08)'
cc = 'cc (Alpine 12.1.1_git20220630) 12.1.1 20220630'
cargo_verbose = '''
cargo 1.65.0-nightly (646e9a0b9 2022-09-02)
release: 1.65.0-nightly
commit-hash: 646e9a0b9ea8354cc409d05f10e8dc752c5de78e
commit-date: 2022-09-02
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (1120c5e01 2022-09-08)
binary: rustc
commit-hash: 1120c5e01df508de64fe6642f22fadeb574afd6d
commit-date: 2022-09-08
host: aarch64-unknown-linux-musl
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
