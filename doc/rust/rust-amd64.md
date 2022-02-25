# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-02-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust_amd64_2022-02-25_03-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9e098829d2bf7815479937a803affa7bfaf766bd4f738293907f7ea8d21d51bc"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1558284288

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "232M"
zstd_bytes = 242532978

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220221"
previous_tag = "2022-02-21"
previous_file = "rust_amd64_2022-02-21_03-02-rootfs.tar.zst"
previous_sha256 = "bfbe09fb27579a3a95f3071dff936fad4888f6c3e69872edba1348f54511a729"

current_version = "latest02"
current_date = "20220225"
old_file = "rust_amd64_2022-02-18_03-00-rootfs.tar.zst"
old_sha256 = "482a30a762ff0ca3d33fcc21f69b5967475e09e79cb53f06aff3291ed51a7e44"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-02-25_03-00-rootfs.tar.zst
# SHA256SUM=9e098829d2bf7815479937a803affa7bfaf766bd4f738293907f7ea8d21d51bc
# BUILD_DATE=20220225
# BUILD_TAG=2022-02-25
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-25
begin = 2022-02-25 02:52:28.152183754+00:00
start-sync_0 = 02:54:06
start-zstd = 02:55:03
start-sync_1 = 02:59:48
end-sync_1 = 03:00:09
end = 2022-02-25 03:00:09.899620048+00:00

[server]
repo = "cake233/rust-amd64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (d6cdde5 2022-02-22)'
rustc = 'rustc 1.61.0-nightly (4b043faba 2022-02-24)'
cc = 'cc (Debian 11.2.0-17) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (d6cdde5 2022-02-22)
release: 1.61.0-nightly
commit-hash: d6cdde584a1f15ea086bae922e20fd27f7165431
commit-date: 2022-02-22
host: x86_64-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (4b043faba 2022-02-24)
binary: rustc
commit-hash: 4b043faba34ccc053a4d0110634c323f6c03765e
commit-date: 2022-02-24
host: x86_64-unknown-linux-gnu
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
