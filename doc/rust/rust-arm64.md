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
tag = ["latest", "2023-08-14", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-08-14_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a3c8095602a5069a8232e49e11b7fbe499685ca9e0bacb3cddb10cdd93dfb7b5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1913462272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "242M"
zstd_bytes = 252961442

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230811"
previous_tag = "2023-08-11"
previous_file = "rust_arm64_2023-08-11_03-12-rootfs.tar.zst"
previous_sha256 = "c32cea724ae48ef5e57fe2269df85be157ed43477fd575f8aa2ef6c40430b4ee"

current_version = "latest01"
current_date = "20230814"
old_file = "rust_arm64_2023-08-07_03-08-rootfs.tar.zst"
old_sha256 = "967d3de579191b39c283f019f5a6b8093982d4d6781f5e6044f95c9dcd9973d3"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-08-14_03-10-rootfs.tar.zst
# SHA256SUM=a3c8095602a5069a8232e49e11b7fbe499685ca9e0bacb3cddb10cdd93dfb7b5
# BUILD_DATE=20230814
# BUILD_TAG=2023-08-14
# STATUS=completed
# VERSION=latest01
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-14
begin = 2023-08-14 02:52:35.709601009+00:00
start-sync_0 = 03:01:08
start-zstd = 03:02:33
start-sync_1 = 03:10:17
end-sync_1 = 03:10:44
end = 2023-08-14 03:10:44.368497503+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (7e9de3f4e 2023-08-13)'
rustc = 'rustc 1.73.0-nightly (1b198b3a1 2023-08-13)'
cc = 'cc (Debian 13.2.0-2) 13.2.0'
cargo_verbose = '''
cargo 1.73.0-nightly (7e9de3f4e 2023-08-13)
release: 1.73.0-nightly
commit-hash: 7e9de3f4ec3708f500bec142317895b96131e47c
commit-date: 2023-08-13
host: aarch64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (1b198b3a1 2023-08-13)
binary: rustc
commit-hash: 1b198b3a196442e14fb06978166ab46a4618d131
commit-date: 2023-08-13
host: aarch64-unknown-linux-gnu
release: 1.73.0-nightly
LLVM version: 17.0.0
'''
```
