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
tag = ["alpine", "2022-03-11", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust-musl_arm64_2022-03-11_02-57.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "c642ea0134f934c9c0c53281297985fd8fd48e490583e988f092e809027a3049"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "721M"
tar_bytes = 755020288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "167M"
zstd_bytes = 174507060

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "rust-musl_arm64_2022-03-07_02-58-rootfs.tar.zst"
previous_sha256 = "ee8ed5c1d13c3753cc8bc9cadcfd074cff774cd96181fb8f3fceb681b785e87a"

current_version = "latest02"
current_date = "20220311"
old_file = "rust-musl_arm64_2022-03-04_02-58-rootfs.tar.zst"
old_sha256 = "dffae27f2058a54557101114d03d7992995a44efbb08047f993428ff0c32f335"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-03-11_02-57-rootfs.tar.zst
# SHA256SUM=c642ea0134f934c9c0c53281297985fd8fd48e490583e988f092e809027a3049
# BUILD_DATE=20220311
# BUILD_TAG=2022-03-11
# STATUS=completed
# VERSION=latest02
# END_TIME=02:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-11
begin = 2022-03-11 02:52:26.172496033+00:00
start-sync_0 = 02:54:12
start-zstd = 02:54:50
start-sync_1 = 02:56:53
end-sync_1 = 02:57:08
end = 2022-03-11 02:57:08.256492764+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.2'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (65c826642 2022-03-09)'
rustc = 'rustc 1.61.0-nightly (5f4e06771 2022-03-10)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.61.0-nightly (65c826642 2022-03-09)
release: 1.61.0-nightly
commit-hash: 65c82664263feddc5fe2d424be0993c28d46377a
commit-date: 2022-03-09
host: aarch64-unknown-linux-musl
libgit2: 1.4.1 (sys:0.14.1 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (5f4e06771 2022-03-10)
binary: rustc
commit-hash: 5f4e0677190b82e61dc507e3e72caf89da8e5e28
commit-date: 2022-03-10
host: aarch64-unknown-linux-musl
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
