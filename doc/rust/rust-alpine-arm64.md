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
tag = ["alpine", "2022-04-25", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "rust-musl_arm64_2022-04-25_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f39af8914266178155a7088763d6d56d61bcdb1474635f2cfdc49647c7bb6de8"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 810944000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "148M"
zstd_bytes = 154867443

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220422"
previous_tag = "2022-04-22"
previous_file = "rust-musl_arm64_2022-04-22_03-01-rootfs.tar.zst"
previous_sha256 = "7f9dad5cd56418c92f2a2e60982357b126c8c0c42f9fb3e8f1b65e6bac123ed9"

current_version = "latest01"
current_date = "20220425"
old_file = "rust-musl_arm64_2022-04-18_03-00-rootfs.tar.zst"
old_sha256 = "accee7debf1e2cbe460a04fbc934d8eae43d936002e83f6ae079fae907248942"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-04-25_02-59-rootfs.tar.zst
# SHA256SUM=f39af8914266178155a7088763d6d56d61bcdb1474635f2cfdc49647c7bb6de8
# BUILD_DATE=20220425
# BUILD_TAG=2022-04-25
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-25
begin = 2022-04-25 02:52:28.786304779+00:00
start-sync_0 = 02:54:16
start-zstd = 02:54:55
start-sync_1 = 02:59:16
end-sync_1 = 02:59:29
end = 2022-04-25 02:59:29.164039379+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.62.0-nightly (edffc4ada 2022-04-19)'
rustc = 'rustc 1.62.0-nightly (18f314e70 2022-04-24)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.62.0-nightly (edffc4ada 2022-04-19)
release: 1.62.0-nightly
commit-hash: edffc4ada3d77799e5a04eeafd9b2f843d29fc23
commit-date: 2022-04-19
host: aarch64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (18f314e70 2022-04-24)
binary: rustc
commit-hash: 18f314e7027fe7084aaab8620c624a0d7bd29e70
commit-date: 2022-04-24
host: aarch64-unknown-linux-musl
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
