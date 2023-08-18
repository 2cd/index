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
tag = ["alpine", "2023-08-18", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-08-18_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5d1a9f428a40da7d34dc28cf35209014f69cdc2ef846b68263525e64a935f38a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "829M"
tar_bytes = 868363776

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "164M"
zstd_bytes = 171962344

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230814"
previous_tag = "2023-08-14"
previous_file = "rust-musl_amd64_2023-08-14_03-00-rootfs.tar.zst"
previous_sha256 = "2d613014268842739af1c68ab161e7a194c44c5f2ac8ff927e137bce82581bd6"

current_version = "latest02"
current_date = "20230818"
old_file = "rust-musl_amd64_2023-08-11_02-59-rootfs.tar.zst"
old_sha256 = "3f08856d41d11963df078f72551f7f61a262da519a7f76ed65bd1b246f8924a6"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-08-18_03-00-rootfs.tar.zst
# SHA256SUM=5d1a9f428a40da7d34dc28cf35209014f69cdc2ef846b68263525e64a935f38a
# BUILD_DATE=20230818
# BUILD_TAG=2023-08-18
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-18
begin = 2023-08-18 02:52:35.274680571+00:00
start-sync_0 = 02:53:50
start-zstd = 02:54:42
start-sync_1 = 03:00:37
end-sync_1 = 03:00:57
end = 2023-08-18 03:00:57.296062658+00:00

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
cargo = 'cargo 1.73.0-nightly (7c3904d6c 2023-08-14)'
rustc = 'rustc 1.73.0-nightly (076887268 2023-08-17)'
cc = 'cc (Alpine 13.1.1_git20230722) 13.1.1 20230722'
cargo_verbose = '''
cargo 1.73.0-nightly (7c3904d6c 2023-08-14)
release: 1.73.0-nightly
commit-hash: 7c3904d6c3ed54e8a413023519b55a536ad44d5b
commit-date: 2023-08-14
host: x86_64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (076887268 2023-08-17)
binary: rustc
commit-hash: 07688726805d5db0a4bca445a6651d09708041ea
commit-date: 2023-08-17
host: x86_64-unknown-linux-musl
release: 1.73.0-nightly
LLVM version: 17.0.0
'''
```
