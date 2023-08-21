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
tag = ["alpine", "2023-08-21", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-08-21_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "e2c1b5ae873f9373aa8144a0aed61df53066baf556ed2f34ef4f7a37f7e6206e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "830M"
tar_bytes = 869330432

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "165M"
zstd_bytes = 172227909

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230818"
previous_tag = "2023-08-18"
previous_file = "rust-musl_amd64_2023-08-18_03-00-rootfs.tar.zst"
previous_sha256 = "5d1a9f428a40da7d34dc28cf35209014f69cdc2ef846b68263525e64a935f38a"

current_version = "latest01"
current_date = "20230821"
old_file = "rust-musl_amd64_2023-08-14_03-00-rootfs.tar.zst"
old_sha256 = "2d613014268842739af1c68ab161e7a194c44c5f2ac8ff927e137bce82581bd6"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-08-21_02-59-rootfs.tar.zst
# SHA256SUM=e2c1b5ae873f9373aa8144a0aed61df53066baf556ed2f34ef4f7a37f7e6206e
# BUILD_DATE=20230821
# BUILD_TAG=2023-08-21
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-21
begin = 2023-08-21 02:52:32.024622118+00:00
start-sync_0 = 02:53:38
start-zstd = 02:54:22
start-sync_1 = 02:59:32
end-sync_1 = 02:59:47
end = 2023-08-21 02:59:47.106290584+00:00

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
cargo = 'cargo 1.74.0-nightly (80eca0e58 2023-08-19)'
rustc = 'rustc 1.74.0-nightly (5c6a7e71c 2023-08-20)'
cc = 'cc (Alpine 13.1.1_git20230722) 13.1.1 20230722'
cargo_verbose = '''
cargo 1.74.0-nightly (80eca0e58 2023-08-19)
release: 1.74.0-nightly
commit-hash: 80eca0e58fb2ff52c1e94fc191b55b37ed73e0e4
commit-date: 2023-08-19
host: x86_64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (5c6a7e71c 2023-08-20)
binary: rustc
commit-hash: 5c6a7e71cd66705c31c9af94077901a220f0870c
commit-date: 2023-08-20
host: x86_64-unknown-linux-musl
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
