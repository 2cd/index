# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-09-15", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-09-15_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "14ac21f56aa46a49622fdf053a03c82dd41d821fbee0e397312893b04ae8528d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "2.0G"
tar_bytes = 2054147584

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "244M"
zstd_bytes = 255838776

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230911"
previous_tag = "2023-09-11"
previous_file = "rust_s390x_2023-09-11_03-08-rootfs.tar.zst"
previous_sha256 = "80fcf1054b60e05366e3442aa5f73c7a2703fbe6ac24d25419c2e1e16ed89fb0"

current_version = "latest02"
current_date = "20230915"
old_file = "rust_s390x_2023-09-08_03-07-rootfs.tar.zst"
old_sha256 = "f6ef8582a8a348d118434e06cf21db2cc385057cecdc700455f43c7f7692848f"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-09-15_03-10-rootfs.tar.zst
# SHA256SUM=14ac21f56aa46a49622fdf053a03c82dd41d821fbee0e397312893b04ae8528d
# BUILD_DATE=20230915
# BUILD_TAG=2023-09-15
# STATUS=completed
# VERSION=latest02
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-15
begin = 2023-09-15 02:52:33.432529006+00:00
start-sync_0 = 03:00:34
start-zstd = 03:02:04
start-sync_1 = 03:09:53
end-sync_1 = 03:10:19
end = 2023-09-15 03:10:19.945635872+00:00

[server]
repo = "cake233/rust-s390x"

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
ldd = 'ldd (Debian GLIBC 2.37-8) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (2fc85d15a 2023-09-09)'
rustc = 'rustc 1.74.0-nightly (ca2b74f1a 2023-09-14)'
cc = 'cc (Debian 13.2.0-4) 13.2.0'
cargo_verbose = '''
cargo 1.74.0-nightly (2fc85d15a 2023-09-09)
release: 1.74.0-nightly
commit-hash: 2fc85d15a542bfb610aff7682073412cf635352f
commit-date: 2023-09-09
host: s390x-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.0 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (ca2b74f1a 2023-09-14)
binary: rustc
commit-hash: ca2b74f1ae5075d62e223c0a91574a1fc3f51c7c
commit-date: 2023-09-14
host: s390x-unknown-linux-gnu
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
