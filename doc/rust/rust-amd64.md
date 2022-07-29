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
tag = ["latest", "2022-07-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-07-29_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "82617150946a0767b1f63f82cd2e877024adfe75ced7284e3d40d06492b332b5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1968400384

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "339M"
zstd_bytes = 355024155

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_amd64_2022-07-18_03-00-rootfs.tar.zst"
previous_sha256 = "db9ac467e42ce5b7fa8fd294c3184da0ce56cea2c63824bf247c2e28602cc34d"

current_version = "latest01"
current_date = "20220729"
old_file = "rust_amd64_2022-07-15_03-01-rootfs.tar.zst"
old_sha256 = "d314d912295a4d94762b3d665b44025a87e97bacf59126606e92ec93fa42bbd6"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-07-29_03-03-rootfs.tar.zst
# SHA256SUM=82617150946a0767b1f63f82cd2e877024adfe75ced7284e3d40d06492b332b5
# BUILD_DATE=20220729
# BUILD_TAG=2022-07-29
# STATUS=completed
# VERSION=latest01
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-29
begin = 2022-07-29 02:52:28.352335346+00:00
start-sync_0 = 02:54:27
start-zstd = 02:55:37
start-sync_1 = 03:03:22
end-sync_1 = 03:03:51
end = 2022-07-29 03:03:51.998483277+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (85b500cca 2022-07-24)'
rustc = 'rustc 1.64.0-nightly (9067d5277 2022-07-28)'
cc = 'cc (Debian 12.1.0-7) 12.1.0'
cargo_verbose = '''
cargo 1.64.0-nightly (85b500cca 2022-07-24)
release: 1.64.0-nightly
commit-hash: 85b500ccad8cd0b63995fd94a03ddd4b83f7905b
commit-date: 2022-07-24
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (9067d5277 2022-07-28)
binary: rustc
commit-hash: 9067d5277d10f0f32a49ec9c125a33828e26a32b
commit-date: 2022-07-28
host: x86_64-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
