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
tag = ["latest", "2023-02-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-02-06_15-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3976f07a52d098324c760beb9ef6f92d56b07db57efd1cb2ec3c7f23d6d56e0e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1864760320

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "244M"
zstd_bytes = 255528408

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230203"
previous_tag = "2023-02-03"
previous_file = "rust_arm64_2023-02-03_03-10-rootfs.tar.zst"
previous_sha256 = "b2943dd41978ee62e1354ca9327ebe8d2cac6c12b6a64ebb04cac49b39945763"

current_version = "latest02"
current_date = "20230206"
old_file = "rust_arm64_2023-01-27_09-06-rootfs.tar.zst"
old_sha256 = "6d46b3561cdc88da28230e1cb1a22bab1f2bef9bd5f6fd4d9d31e2ebde70e832"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-02-06_15-32-rootfs.tar.zst
# SHA256SUM=3976f07a52d098324c760beb9ef6f92d56b07db57efd1cb2ec3c7f23d6d56e0e
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest02
# END_TIME=15:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 15:19:12.394897464+00:00
start-sync_0 = 15:25:36
start-zstd = 15:26:48
start-sync_1 = 15:32:21
end-sync_1 = 15:32:44
end = 2023-02-06 15:32:44.858066096+00:00

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
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.69.0-nightly (e84a7928d 2023-01-31)'
rustc = 'rustc 1.69.0-nightly (75a0be98f 2023-02-05)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (e84a7928d 2023-01-31)
release: 1.69.0-nightly
commit-hash: e84a7928d93a31f284b497c214a2ece69b4d7719
commit-date: 2023-01-31
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (75a0be98f 2023-02-05)
binary: rustc
commit-hash: 75a0be98f25a4b9de5afa0e15eb016e7f9627032
commit-date: 2023-02-05
host: aarch64-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
