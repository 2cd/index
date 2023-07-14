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
tag = ["alpine", "2023-07-14", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-07-14_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fbbf25215628d44ade9cd26ed6122cc076f36a76827f25f33d6d1e2c05289768"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "866M"
tar_bytes = 908033536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 164825788

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230710"
previous_tag = "2023-07-10"
previous_file = "rust-musl_arm64_2023-07-10_03-00-rootfs.tar.zst"
previous_sha256 = "7ccb97e3fabe3008a160517142d124fbee716d60dfa5df87c221f088b8806414"

current_version = "latest02"
current_date = "20230714"
old_file = "rust-musl_arm64_2023-07-07_03-00-rootfs.tar.zst"
old_sha256 = "400a1e23875f81815299dc8c2c557eb8edfc95180cb6da12e97d6eabfcf7791a"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-07-14_03-01-rootfs.tar.zst
# SHA256SUM=fbbf25215628d44ade9cd26ed6122cc076f36a76827f25f33d6d1e2c05289768
# BUILD_DATE=20230714
# BUILD_TAG=2023-07-14
# STATUS=completed
# VERSION=latest02
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-14
begin = 2023-07-14 02:52:40.811989784+00:00
start-sync_0 = 02:55:00
start-zstd = 02:55:45
start-sync_1 = 03:00:50
end-sync_1 = 03:01:05
end = 2023-07-14 03:01:05.919605417+00:00

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
cargo = 'cargo 1.73.0-nightly (694a57956 2023-07-11)'
rustc = 'rustc 1.73.0-nightly (7bd81ee19 2023-07-13)'
cc = 'cc (Alpine 13.1.1_git20230708) 13.1.1 20230708'
cargo_verbose = '''
cargo 1.73.0-nightly (694a57956 2023-07-11)
release: 1.73.0-nightly
commit-hash: 694a579566a9a1482b20aff8a68f0e4edd99bd28
commit-date: 2023-07-11
host: aarch64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (7bd81ee19 2023-07-13)
binary: rustc
commit-hash: 7bd81ee1902c049691d0a1f03be5558bee51d100
commit-date: 2023-07-13
host: aarch64-unknown-linux-musl
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
