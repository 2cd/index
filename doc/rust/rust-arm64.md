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
tag = ["latest", "2023-01-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-01-23_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9c012e83f646f88d2b2684684b7349b12f24d5e9f1eec86c6437561e26ee1df5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1869122048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "244M"
zstd_bytes = 255843783

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230120"
previous_tag = "2023-01-20"
previous_file = "rust_arm64_2023-01-20_03-06-rootfs.tar.zst"
previous_sha256 = "1e051f68d5e191a105805ecb5a9d53ea69e238015abbb3bf53494f5cf352e163"

current_version = "latest01"
current_date = "20230123"
old_file = "rust_arm64_2023-01-13_09-07-rootfs.tar.zst"
old_sha256 = "6b61927bc0b2889a08f037b6ffabe8d7ff1ce7a0902f0624b558b69370170e4e"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-01-23_03-05-rootfs.tar.zst
# SHA256SUM=9c012e83f646f88d2b2684684b7349b12f24d5e9f1eec86c6437561e26ee1df5
# BUILD_DATE=20230123
# BUILD_TAG=2023-01-23
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-23
begin = 2023-01-23 02:52:23.274759220+00:00
start-sync_0 = 02:58:51
start-zstd = 02:59:56
start-sync_1 = 03:05:36
end-sync_1 = 03:05:55
end = 2023-01-23 03:05:55.129748630+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.69.0-nightly (985d561f0 2023-01-20)'
rustc = 'rustc 1.69.0-nightly (5e37043d6 2023-01-22)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (985d561f0 2023-01-20)
release: 1.69.0-nightly
commit-hash: 985d561f0bb9b76ec043a2b12511790ec7a2b954
commit-date: 2023-01-20
host: aarch64-unknown-linux-gnu
libgit2: 1.5.1 (sys:0.16.1 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (5e37043d6 2023-01-22)
binary: rustc
commit-hash: 5e37043d63bfe2f3be8fa5a05b07d6c0dad5775d
commit-date: 2023-01-22
host: aarch64-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
