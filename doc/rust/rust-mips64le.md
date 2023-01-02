# rust-mips64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```sh
docker exec -it rust-mips64le bash
```
<!-- repo=cake233/rust-mips64le -->

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
    cake233/rust-mips64le \
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
    cake233/rust-mips64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-01-02", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2023-01-02_11-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "15ac3722796ad6be91ff76e5ceff25581a98e2b21ec81289016e69faaa8d25a5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1679904256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "195M"
zstd_bytes = 203516996

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221230"
previous_tag = "2022-12-30"
previous_file = "rust_mips64el_2022-12-30_03-05-rootfs.tar.zst"
previous_sha256 = "fb23f8d371fd434d25245deb095f42eb0706a2ffe2cb082fb71a0c2a733cb4d3"

current_version = "latest02"
current_date = "20230102"
old_file = "rust_mips64el_2022-12-26_03-08-rootfs.tar.zst"
old_sha256 = "d3e6b5128848e2e36fc7af0a61aa95a8f5d5259cdcb6e62a40c88547f94612df"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2023-01-02_11-06-rootfs.tar.zst
# SHA256SUM=15ac3722796ad6be91ff76e5ceff25581a98e2b21ec81289016e69faaa8d25a5
# BUILD_DATE=20230102
# BUILD_TAG=2023-01-02
# STATUS=completed
# VERSION=latest02
# END_TIME=11:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-02
begin = 2023-01-02 10:51:12.275297696+00:00
start-sync_0 = 10:59:04
start-zstd = 11:00:15
start-sync_1 = 11:06:27
end-sync_1 = 11:06:49
end = 2023-01-02 11:06:49.023013573+00:00

[server]
repo = "cake233/rust-mips64le"

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
ldd = 'ldd (Debian GLIBC 2.36-7) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.68.0-nightly (2381cbdb4 2022-12-23)'
rustc = 'rustc 1.68.0-nightly (77429957a 2023-01-01)'
cc = 'cc (Debian 12.2.0-12) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (2381cbdb4 2022-12-23)
release: 1.68.0-nightly
commit-hash: 2381cbdb4e9b07090f552d34a44a529b6e620e44
commit-date: 2022-12-23
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (77429957a 2023-01-01)
binary: rustc
commit-hash: 77429957a0e9c90a26c89def061ffdd4bae5ccb9
commit-date: 2023-01-01
host: mips64el-unknown-linux-gnuabi64
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
