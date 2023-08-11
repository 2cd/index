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
tag = ["latest", "2023-08-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-08-11_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f8688456d1b2dbae64209750c5834daf0b8802e776cf175d01451f29f9e3e30a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1598688256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237919203

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230807"
previous_tag = "2023-08-07"
previous_file = "rust_amd64_2023-08-07_03-03-rootfs.tar.zst"
previous_sha256 = "629ae1555bc14c25d173d18db31cea902db6077ccf47717d63750b27bb9ed352"

current_version = "latest02"
current_date = "20230811"
old_file = "rust_amd64_2023-08-04_03-02-rootfs.tar.zst"
old_sha256 = "66dab69c1a2042aa721b2114b6c042d576d1f4dcdbea00913ce1ff2b8159e01c"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-08-11_03-00-rootfs.tar.zst
# SHA256SUM=f8688456d1b2dbae64209750c5834daf0b8802e776cf175d01451f29f9e3e30a
# BUILD_DATE=20230811
# BUILD_TAG=2023-08-11
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-11
begin = 2023-08-11 02:52:31.429751611+00:00
start-sync_0 = 02:54:01
start-zstd = 02:54:59
start-sync_1 = 02:59:38
end-sync_1 = 03:00:05
end = 2023-08-11 03:00:05.226257606+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (d78bbf4bd 2023-08-03)'
rustc = 'rustc 1.73.0-nightly (439d066bc 2023-08-10)'
cc = 'cc (Debian 13.2.0-2) 13.2.0'
cargo_verbose = '''
cargo 1.73.0-nightly (d78bbf4bd 2023-08-03)
release: 1.73.0-nightly
commit-hash: d78bbf4bde3c6b95caca7512f537c6f9721426ff
commit-date: 2023-08-03
host: x86_64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Debian [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (439d066bc 2023-08-10)
binary: rustc
commit-hash: 439d066bcf9496b1b8c8dde8bef3bce607a621bb
commit-date: 2023-08-10
host: x86_64-unknown-linux-gnu
release: 1.73.0-nightly
LLVM version: 17.0.0
'''
```
