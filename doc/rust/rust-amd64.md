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
tag = ["latest", "2022-07-04", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-07-04_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "64d132bb056ed3f48695923ee2f1c5de9fc288ea630755c47f982203fa81744c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1599829504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "240M"
zstd_bytes = 251013629

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220701"
previous_tag = "2022-07-01"
previous_file = "rust_amd64_2022-07-01_02-59-rootfs.tar.zst"
previous_sha256 = "7e5fb530ab62858f0d29d0e3d0061f518e6b8716e0428cc5025c71a1cd5ce0e9"

current_version = "latest02"
current_date = "20220704"
old_file = "rust_amd64_2022-06-27_02-59-rootfs.tar.zst"
old_sha256 = "e1d445ada5b5f32a75fa2859fe951343c52bfd4f1764d010c987160e1a88060a"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-07-04_03-00-rootfs.tar.zst
# SHA256SUM=64d132bb056ed3f48695923ee2f1c5de9fc288ea630755c47f982203fa81744c
# BUILD_DATE=20220704
# BUILD_TAG=2022-07-04
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-04
begin = 2022-07-04 02:52:31.175082945+00:00
start-sync_0 = 02:54:12
start-zstd = 02:55:09
start-sync_1 = 03:00:08
end-sync_1 = 03:00:45
end = 2022-07-04 03:00:45.957123020+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.64.0-nightly (dbff32b27 2022-06-24)'
rustc = 'rustc 1.64.0-nightly (495b21669 2022-07-03)'
cc = 'cc (Debian 11.3.0-4) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (dbff32b27 2022-06-24)
release: 1.64.0-nightly
commit-hash: dbff32b27893b899ae2397f3d56d1be111041d56
commit-date: 2022-06-24
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (495b21669 2022-07-03)
binary: rustc
commit-hash: 495b216696ccbc27c73d6bdc486bf4621d610f4b
commit-date: 2022-07-03
host: x86_64-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
