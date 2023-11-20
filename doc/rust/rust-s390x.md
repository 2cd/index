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
tag = ["latest", "2023-11-20", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-11-20_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "10ecd125d2b5fd8aa2895640d0d3c881af777dcae35837245a042004b6fef3d3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 1943256064

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "245M"
zstd_bytes = 256489365

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231113"
previous_tag = "2023-11-13"
previous_file = "rust_s390x_2023-11-13_03-06-rootfs.tar.zst"
previous_sha256 = "5bdc40105446edee749f1c9e4a4d0d88dd46e5e4545a5640a284579ad15fff8d"

current_version = "latest02"
current_date = "20231120"
old_file = "rust_s390x_2023-11-10_03-10-rootfs.tar.zst"
old_sha256 = "559bde547e61018a0caf79ef6a0de1f6291b07da13dcbd6bcf679a62d182ca09"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-11-20_03-04-rootfs.tar.zst
# SHA256SUM=10ecd125d2b5fd8aa2895640d0d3c881af777dcae35837245a042004b6fef3d3
# BUILD_DATE=20231120
# BUILD_TAG=2023-11-20
# STATUS=completed
# VERSION=latest02
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-20
begin = 2023-11-20 02:52:33.839682488+00:00
start-sync_0 = 02:57:57
start-zstd = 02:58:54
start-sync_1 = 03:03:45
end-sync_1 = 03:04:03
end = 2023-11-20 03:04:03.539828365+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.76.0-nightly (9765a449d 2023-11-17)'
rustc = 'rustc 1.76.0-nightly (9a66e4471 2023-11-19)'
cc = 'cc (Debian 13.2.0-6) 13.2.0'
cargo_verbose = '''
cargo 1.76.0-nightly (9765a449d 2023-11-17)
release: 1.76.0-nightly
commit-hash: 9765a449d9b7341c2b49b88da41c2268ea599720
commit-date: 2023-11-17
host: s390x-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.76.0-nightly (9a66e4471 2023-11-19)
binary: rustc
commit-hash: 9a66e4471f71283fd54d80ef8147630d34756332
commit-date: 2023-11-19
host: s390x-unknown-linux-gnu
release: 1.76.0-nightly
LLVM version: 17.0.5
'''
```
