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
tag = ["latest", "2022-04-16", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
x11_or_wayland = false
syntax_version = "0.0.0-alpha.3"

[file]
name = "rust_s390x_2022-04-16_17-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4ffe62391e71844a6770e8d7d3eff33f77b84df32e721a5004b58c527c5c663a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1775086080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258494606

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220415"
previous_tag = "2022-04-15"
previous_file = "rust_s390x_2022-04-15_03-06-rootfs.tar.zst"
previous_sha256 = "0a18d9ac18cd8b6414af940d0786d7c1873560f587c04f057b7a57ff2c864c19"

current_version = "latest02"
current_date = "20220416"
old_file = "rust_s390x_2022-04-11_02-08-rootfs.tar.zst"
old_sha256 = "1449608d38c5ad09516c87cf986882a172209c0ae0758a622c4f06c5db29cac8"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-04-16_17-08-rootfs.tar.zst
# SHA256SUM=4ffe62391e71844a6770e8d7d3eff33f77b84df32e721a5004b58c527c5c663a
# BUILD_DATE=20220416
# BUILD_TAG=2022-04-16
# STATUS=completed
# VERSION=latest02
# END_TIME=17:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-16
begin = 2022-04-16 16:55:10.992884587+00:00
start-sync_0 = 17:01:20
start-zstd = 17:02:25
start-sync_1 = 17:07:55
end-sync_1 = 17:08:14
end = 2022-04-16 17:08:14.925557372+00:00

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
cargo = 'cargo 1.62.0-nightly (dba5baf43 2022-04-13)'
rustc = 'rustc 1.62.0-nightly (3f391b845 2022-04-15)'
cc = 'cc (Debian 11.2.0-20) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (dba5baf43 2022-04-13)
release: 1.62.0-nightly
commit-hash: dba5baf4345858c591517b24801902a062c399f8
commit-date: 2022-04-13
host: s390x-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (3f391b845 2022-04-15)
binary: rustc
commit-hash: 3f391b84552f210adec7893b50c5da74f9362ae4
commit-date: 2022-04-15
host: s390x-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.0
'''
```
