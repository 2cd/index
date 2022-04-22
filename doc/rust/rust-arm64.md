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
tag = ["latest", "2022-04-22", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "rust_arm64_2022-04-22_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "04cbcdd7c7ad18d03d461271322a9a4b91c563e3887908e45f933767b23ac96d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1816705536

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "257M"
zstd_bytes = 268913833

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220418"
previous_tag = "2022-04-18"
previous_file = "rust_arm64_2022-04-18_03-05-rootfs.tar.zst"
previous_sha256 = "9d38f4bcd30ac39a0439dbd05f77b8df4aaca815ee60003bb2000caea0d4902a"

current_version = "latest02"
current_date = "20220422"
old_file = "rust_arm64_2022-04-15_03-05-rootfs.tar.zst"
old_sha256 = "eaa72b77a86fcc230b77cb59d854c368f7b4355fde7059173d8db3967239a570"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-04-22_03-05-rootfs.tar.zst
# SHA256SUM=04cbcdd7c7ad18d03d461271322a9a4b91c563e3887908e45f933767b23ac96d
# BUILD_DATE=20220422
# BUILD_TAG=2022-04-22
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-22
begin = 2022-04-22 02:52:28.317159289+00:00
start-sync_0 = 02:58:05
start-zstd = 02:59:04
start-sync_1 = 03:04:49
end-sync_1 = 03:05:08
end = 2022-04-22 03:05:08.953509486+00:00

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
cargo = 'cargo 1.62.0-nightly (edffc4a 2022-04-19)'
rustc = 'rustc 1.62.0-nightly (de1bc0008 2022-04-21)'
cc = 'cc (Debian 11.2.0-20) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (edffc4a 2022-04-19)
release: 1.62.0-nightly
commit-hash: edffc4ada3d77799e5a04eeafd9b2f843d29fc23
commit-date: 2022-04-19
host: aarch64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (de1bc0008 2022-04-21)
binary: rustc
commit-hash: de1bc0008be096cf7ed67b93402250d3b3e480d0
commit-date: 2022-04-21
host: aarch64-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
