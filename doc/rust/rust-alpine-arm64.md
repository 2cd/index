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
tag = ["alpine", "2022-01-03", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust-musl_arm64_2022-01-03_02-58.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8a565963e41ceba448dae8669d2c9f9f71434d31924d7196fe87bcdd9e7c4f07"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "774M"
tar_bytes = 810745344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "181M"
zstd_bytes = 189077099

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211231"
previous_tag = "2021-12-31"
previous_file = "rust-musl_arm64_2021-12-31_02-57-rootfs.tar.zst"
previous_sha256 = "3f72e5f0f3a27251908d0c92b691be94de7de4b9e389abb1d36871146eab1b57"

current_version = "latest01"
current_date = "20220103"
old_file = "rust-musl_arm64_2021-12-27_02-58-rootfs.tar.zst"
old_sha256 = "c37b6350ef03b114270c68d72f111a05944c6696fd84ae6fa8886fa879c8325a"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-01-03_02-58-rootfs.tar.zst
# SHA256SUM=8a565963e41ceba448dae8669d2c9f9f71434d31924d7196fe87bcdd9e7c4f07
# BUILD_DATE=20220103
# BUILD_TAG=2022-01-03
# STATUS=completed
# VERSION=latest01
# END_TIME=02:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-03
begin = 2022-01-03 02:52:26.313762464+00:00
start-sync_0 = 02:54:45
start-zstd = 02:55:35
start-sync_1 = 02:58:00
end-sync_1 = 02:58:21
end = 2022-01-03 02:58:21.440664521+00:00

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
cargo = 'cargo 1.59.0-nightly (fcef61230 2021-12-17)'
rustc = 'rustc 1.59.0-nightly (8f3238f89 2022-01-02)'
cc = 'cc (Alpine 11.2.1_git20211128) 11.2.1 20211128'
cargo_verbose = '''
cargo 1.59.0-nightly (fcef61230 2021-12-17)
release: 1.59.0-nightly
commit-hash: fcef61230c3b6213b6b0d233a36ba4ebd1649ec3
commit-date: 2021-12-17
host: aarch64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (8f3238f89 2022-01-02)
binary: rustc
commit-hash: 8f3238f898163f09726c3d2b2cc9bafb09da26f3
commit-date: 2022-01-02
host: aarch64-unknown-linux-musl
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
