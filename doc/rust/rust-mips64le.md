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
tag = ["latest", "2023-07-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2023-07-03_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a64fd4d12e3043cf542fc2e085f9fc7467bccdc0867387174471622089952e98"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1670135808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 205581721

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230626"
previous_tag = "2023-06-26"
previous_file = "rust_mips64el_2023-06-26_03-08-rootfs.tar.zst"
previous_sha256 = "9c20e1d29e9e174532008c7c1e00bbf9bdfb5ac14ca42ab2a829c51f37b414ac"

current_version = "latest02"
current_date = "20230703"
old_file = "rust_mips64el_2023-06-09_03-04-rootfs.tar.zst"
old_sha256 = "1d6121c1b35c46a21380d6130680bb08e289c96a65bbf1da18a2fb1daf074b1a"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2023-07-03_03-04-rootfs.tar.zst
# SHA256SUM=a64fd4d12e3043cf542fc2e085f9fc7467bccdc0867387174471622089952e98
# BUILD_DATE=20230703
# BUILD_TAG=2023-07-03
# STATUS=completed
# VERSION=latest02
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-03
begin = 2023-07-03 02:52:35.019653268+00:00
start-sync_0 = 02:58:20
start-zstd = 02:59:21
start-sync_1 = 03:04:39
end-sync_1 = 03:04:58
end = 2023-07-03 03:04:58.036224545+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-3) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (5b377cece 2023-06-30)'
rustc = 'rustc 1.72.0-nightly (839e9a6e1 2023-07-02)'
cc = 'cc (Debian 12.3.0-5) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (5b377cece 2023-06-30)
release: 1.72.0-nightly
commit-hash: 5b377cece0e0dd0af686cf53ce4637d5d85c2a10
commit-date: 2023-06-30
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (839e9a6e1 2023-07-02)
binary: rustc
commit-hash: 839e9a6e1210934fd24b15548b811a97c77138fc
commit-date: 2023-07-02
host: mips64el-unknown-linux-gnuabi64
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```