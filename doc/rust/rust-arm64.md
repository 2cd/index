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
tag = ["latest", "2023-07-21", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2023-07-21_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "2872bf73975776430ff3ba5b31d73a5c800d399365bd764eb7ad307de750847b"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.1G"
tar_bytes = 2179745280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "331M"
zstd_bytes = 346531528

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230717"
previous_tag = "2023-07-17"
previous_file = "rust_arm64_2023-07-17_03-08-rootfs.tar.zst"
previous_sha256 = "09b3a4e65b0ad161e41fe260065911f40f11ac30b50ef2c819225e192b89e342"

current_version = "latest01"
current_date = "20230721"
old_file = "rust_arm64_2023-07-14_03-08-rootfs.tar.zst"
old_sha256 = "ab084615cf19f795ea5173669885b168dc7a60240f1d3a2d3caed27325377685"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2023-07-21_03-09-rootfs.tar.zst
# SHA256SUM=2872bf73975776430ff3ba5b31d73a5c800d399365bd764eb7ad307de750847b
# BUILD_DATE=20230721
# BUILD_TAG=2023-07-21
# STATUS=completed
# VERSION=latest01
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-21
begin = 2023-07-21 02:52:35.925693895+00:00
start-sync_0 = 03:00:07
start-zstd = 03:01:18
start-sync_1 = 03:09:06
end-sync_1 = 03:09:30
end = 2023-07-21 03:09:30.830154068+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-6) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (1b1555676 2023-07-18)'
rustc = 'rustc 1.73.0-nightly (399b06823 2023-07-20)'
cc = 'cc (Debian 13.1.0-8) 13.1.0'
cargo_verbose = '''
cargo 1.73.0-nightly (1b1555676 2023-07-18)
release: 1.73.0-nightly
commit-hash: 1b15556767f4b78a64e868eedf4073c423f02b93
commit-date: 2023-07-18
host: aarch64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (399b06823 2023-07-20)
binary: rustc
commit-hash: 399b068235ceea440540539b3bfd1aeb82214a28
commit-date: 2023-07-20
host: aarch64-unknown-linux-gnu
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
