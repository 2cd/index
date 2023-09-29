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
tag = ["latest", "2023-09-29", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-09-29_03-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ea812373440a723d3ee5c5dbd7b149107f81b45dbf6b8abd4dfb6be1eedd2ddf"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 2025434624

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "244M"
zstd_bytes = 255809345

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230925"
previous_tag = "2023-09-25"
previous_file = "rust_arm64_2023-09-25_03-12-rootfs.tar.zst"
previous_sha256 = "c28c394bc1422c8360d56caea4431725de83c1615132eacd295cb91072055af6"

current_version = "latest02"
current_date = "20230929"
old_file = "rust_arm64_2023-09-22_03-12-rootfs.tar.zst"
old_sha256 = "437df08ec5f3093f245a65d6900de068d84810d61f4950e6b5329996c41d5d0c"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-09-29_03-15-rootfs.tar.zst
# SHA256SUM=ea812373440a723d3ee5c5dbd7b149107f81b45dbf6b8abd4dfb6be1eedd2ddf
# BUILD_DATE=20230929
# BUILD_TAG=2023-09-29
# STATUS=completed
# VERSION=latest02
# END_TIME=03:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-29
begin = 2023-09-29 02:52:34.974097570+00:00
start-sync_0 = 03:05:49
start-zstd = 03:07:11
start-sync_1 = 03:14:40
end-sync_1 = 03:15:11
end = 2023-09-29 03:15:11.866133729+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-11) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (e6aabe8b3 2023-09-26)'
rustc = 'rustc 1.74.0-nightly (7b4d9e155 2023-09-28)'
cc = 'cc (Debian 13.2.0-4) 13.2.0'
cargo_verbose = '''
cargo 1.74.0-nightly (e6aabe8b3 2023-09-26)
release: 1.74.0-nightly
commit-hash: e6aabe8b3fcf639be3a5bf68e77853bd7b3fa27d
commit-date: 2023-09-26
host: aarch64-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.0 vendored)
libcurl: 8.3.0-DEV (sys:0.4.66+curl-8.3.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (7b4d9e155 2023-09-28)
binary: rustc
commit-hash: 7b4d9e155fec06583c763f176fc432dc779f1fc6
commit-date: 2023-09-28
host: aarch64-unknown-linux-gnu
release: 1.74.0-nightly
LLVM version: 17.0.2
'''
```
