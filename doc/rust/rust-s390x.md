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
tag = ["latest", "2023-05-12", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-05-12_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9ef01274bfe1a3d965614b98988fd17c0eb7cd32441a50895cd6059caa506439"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1869381632

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "237M"
zstd_bytes = 248199860

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230508"
previous_tag = "2023-05-08"
previous_file = "rust_s390x_2023-05-08_03-06-rootfs.tar.zst"
previous_sha256 = "2606184b69bbfde0b212349aa95f6fd73a1183ebd00cfd79fd88985f6742d1f6"

current_version = "latest01"
current_date = "20230512"
old_file = "rust_s390x_2023-05-05_03-06-rootfs.tar.zst"
old_sha256 = "9d9b746db2e4564ecb332c54ec42eb024c8668c5d3531161cab6b75b1a4eadf3"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-05-12_03-08-rootfs.tar.zst
# SHA256SUM=9ef01274bfe1a3d965614b98988fd17c0eb7cd32441a50895cd6059caa506439
# BUILD_DATE=20230512
# BUILD_TAG=2023-05-12
# STATUS=completed
# VERSION=latest01
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-12
begin = 2023-05-12 02:52:37.994378064+00:00
start-sync_0 = 03:00:21
start-zstd = 03:01:44
start-sync_1 = 03:08:14
end-sync_1 = 03:08:37
end = 2023-05-12 03:08:37.841015508+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.71.0-nightly (26b73d15a 2023-05-09)'
rustc = 'rustc 1.71.0-nightly (2a8221dbd 2023-05-11)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.71.0-nightly (26b73d15a 2023-05-09)
release: 1.71.0-nightly
commit-hash: 26b73d15a68fb94579f6d3590585ec0e9d81d3d5
commit-date: 2023-05-09
host: s390x-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (2a8221dbd 2023-05-11)
binary: rustc
commit-hash: 2a8221dbdfd180a2d56d4b0089f4f3952d8c2bcd
commit-date: 2023-05-11
host: s390x-unknown-linux-gnu
release: 1.71.0-nightly
LLVM version: 16.0.2
'''
```
