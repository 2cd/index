# rust-riscv64

## How to run it?

```sh
docker run \
    -it \
    --name rust-riscv64 \
    cake233/rust-riscv64
```

## How to exec shell?

```sh
docker exec -it rust-riscv64 bash
```
<!-- repo=cake233/rust-riscv64 -->

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
    cake233/rust-riscv64 \
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
    cake233/rust-riscv64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-riscv64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-05-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-05-23_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "01add7a72c22396844e4e4fee1e3fac372f9560094fe0cf1215632d2c6c619c2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1690031616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 231749429

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220520"
previous_tag = "2022-05-20"
previous_file = "rust_riscv64_2022-05-20_03-05-rootfs.tar.zst"
previous_sha256 = "c821dc8082d6941c6ac46bf869ed2864d5c3f9838455be8805fe962d9ff062e6"

current_version = "latest02"
current_date = "20220523"
old_file = "rust_riscv64_2022-05-16_03-05-rootfs.tar.zst"
old_sha256 = "04d038491493e625bc69ff35bef3ab73f06193b1c2b069886afd76222d76c214"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-05-23_03-05-rootfs.tar.zst
# SHA256SUM=01add7a72c22396844e4e4fee1e3fac372f9560094fe0cf1215632d2c6c619c2
# BUILD_DATE=20220523
# BUILD_TAG=2022-05-23
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-23
begin = 2022-05-23 02:52:37.044616185+00:00
start-sync_0 = 02:58:23
start-zstd = 02:59:18
start-sync_1 = 03:04:52
end-sync_1 = 03:05:10
end = 2022-05-23 03:05:10.595008501+00:00

[server]
repo = "cake233/rust-riscv64"

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
cargo = 'cargo 1.63.0-nightly (a4c1cd0eb 2022-05-18)'
rustc = 'rustc 1.63.0-nightly (b2eed72a6 2022-05-22)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (a4c1cd0eb 2022-05-18)
release: 1.63.0-nightly
commit-hash: a4c1cd0eb6b18082a7e693f5a665548fe1534be4
commit-date: 2022-05-18
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (b2eed72a6 2022-05-22)
binary: rustc
commit-hash: b2eed72a6fbf254e7d44942eaa121fcbed05d3fb
commit-date: 2022-05-22
host: riscv64gc-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.4
'''
```
