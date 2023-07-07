# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-07-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-07-07_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f3e2f622c8407ffb2860abfd7d41aca3c0b0218c5c7295571240ae417ac53e6a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1874790400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "246M"
zstd_bytes = 257419445

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230703"
previous_tag = "2023-07-03"
previous_file = "rust_arm64_2023-07-03_03-05-rootfs.tar.zst"
previous_sha256 = "a0480858d9ec24d9a59f4b51b7017eb99b3a4c1bc1daa831812f572819202298"

current_version = "latest01"
current_date = "20230707"
old_file = "rust_arm64_2023-06-30_03-05-rootfs.tar.zst"
old_sha256 = "788d00feeea8c492209be2f7133d44c266e0ffb8462c73ae4156925e4876ad7d"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-07-07_03-05-rootfs.tar.zst
# SHA256SUM=f3e2f622c8407ffb2860abfd7d41aca3c0b0218c5c7295571240ae417ac53e6a
# BUILD_DATE=20230707
# BUILD_TAG=2023-07-07
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-07
begin = 2023-07-07 02:52:30.013312464+00:00
start-sync_0 = 02:58:16
start-zstd = 02:59:24
start-sync_1 = 03:05:11
end-sync_1 = 03:05:30
end = 2023-07-07 03:05:30.642086704+00:00

[server]
repo = "cake233/rust-arm64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.37-3) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (5b377cece 2023-06-30)'
rustc = 'rustc 1.72.0-nightly (85bf07972 2023-07-06)'
cc = 'cc (Debian 12.3.0-5) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (5b377cece 2023-06-30)
release: 1.72.0-nightly
commit-hash: 5b377cece0e0dd0af686cf53ce4637d5d85c2a10
commit-date: 2023-06-30
host: aarch64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (85bf07972 2023-07-06)
binary: rustc
commit-hash: 85bf07972a1041b9e25393b803d0e006bec3eaaf
commit-date: 2023-07-06
host: aarch64-unknown-linux-gnu
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
