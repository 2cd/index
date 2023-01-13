# rust-ppc64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```sh
docker exec -it rust-ppc64le bash
```
<!-- repo=cake233/rust-ppc64le -->

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
    cake233/rust-ppc64le \
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
    cake233/rust-ppc64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-01-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-01-13_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "369baf6d582691b8296fc867b81de0db5c4884b812ff2f42dc69a169f1b59789"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1706713088

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "219M"
zstd_bytes = 229553497

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230109"
previous_tag = "2023-01-09"
previous_file = "rust_ppc64el_2023-01-09_03-11-rootfs.tar.zst"
previous_sha256 = "1d0e1252e0a3dd08bcf7e9b8bef629f298773f10e35fef16951df6182d556a6a"

current_version = "latest01"
current_date = "20230113"
old_file = "rust_ppc64el_2023-01-06_03-06-rootfs.tar.zst"
old_sha256 = "39df440833eae579e14369c1f14c30b0f52336e2edc256ac5d73b5c2286134fa"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-01-13_03-05-rootfs.tar.zst
# SHA256SUM=369baf6d582691b8296fc867b81de0db5c4884b812ff2f42dc69a169f1b59789
# BUILD_DATE=20230113
# BUILD_TAG=2023-01-13
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-13
begin = 2023-01-13 02:52:29.987563791+00:00
start-sync_0 = 02:58:31
start-zstd = 02:59:29
start-sync_1 = 03:04:44
end-sync_1 = 03:05:03
end = 2023-01-13 03:05:03.130884588+00:00

[server]
repo = "cake233/rust-ppc64le"

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
cargo = 'cargo 1.68.0-nightly (d992ab4e9 2023-01-10)'
rustc = 'rustc 1.68.0-nightly (61a415be5 2023-01-12)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (d992ab4e9 2023-01-10)
release: 1.68.0-nightly
commit-hash: d992ab4e9034930e7809749f04077045af8f4d79
commit-date: 2023-01-10
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (61a415be5 2023-01-12)
binary: rustc
commit-hash: 61a415be590113b4935464ef0aaf3b4e7713a077
commit-date: 2023-01-12
host: powerpc64le-unknown-linux-gnu
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
