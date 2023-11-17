# rust-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-amd64 bash
```
<!-- repo=cake233/rust-alpine-amd64 -->

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
    cake233/rust-alpine-amd64 \
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
    cake233/rust-alpine-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2023-11-17", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-11-17_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "37e154fced4c4c8f91dbe75774a48763c1689012fd2a272577ba3237b4b3584b"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "819M"
tar_bytes = 858228736

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "166M"
zstd_bytes = 173366460

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231113"
previous_tag = "2023-11-13"
previous_file = "rust-musl_amd64_2023-11-13_03-00-rootfs.tar.zst"
previous_sha256 = "690c5a5f79307982ccc5639ece29e79750161d15e13dd1deae1103fe5606d1f6"

current_version = "latest02"
current_date = "20231117"
old_file = "rust-musl_amd64_2023-10-27_03-01-rootfs.tar.zst"
old_sha256 = "9c98f1ef2a8cc7743b474c5af9805991b8adb8741c8bb1128c45d21d19e4b090"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-11-17_02-59-rootfs.tar.zst
# SHA256SUM=37e154fced4c4c8f91dbe75774a48763c1689012fd2a272577ba3237b4b3584b
# BUILD_DATE=20231117
# BUILD_TAG=2023-11-17
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-17
begin = 2023-11-17 02:52:31.386315820+00:00
start-sync_0 = 02:54:25
start-zstd = 02:54:56
start-sync_1 = 02:59:41
end-sync_1 = 02:59:54
end = 2023-11-17 02:59:54.029426241+00:00

[server]
repo = "cake233/rust-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.4_git20230717'
rustup = 'rustup 1.26.0 (2023-04-05)'
cargo = 'cargo 1.76.0-nightly (2c03e0e2d 2023-11-16)'
rustc = 'rustc 1.76.0-nightly (a57770440 2023-11-16)'
cc = 'cc (Alpine 13.2.1_git20231014) 13.2.1 20231014'
cargo_verbose = '''
cargo 1.76.0-nightly (2c03e0e2d 2023-11-16)
release: 1.76.0-nightly
commit-hash: 2c03e0e2dcd05dd064fcf10cc1050d342eaf67e3
commit-date: 2023-11-16
host: x86_64-unknown-linux-musl
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.19_alpha20230901 [64-bit]
'''
rustc_verbose = '''
rustc 1.76.0-nightly (a57770440 2023-11-16)
binary: rustc
commit-hash: a57770440f1ebe5b992551d3bcc489ae211908d4
commit-date: 2023-11-16
host: x86_64-unknown-linux-musl
release: 1.76.0-nightly
LLVM version: 17.0.5
'''
```
