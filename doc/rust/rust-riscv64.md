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
tag = ["latest", "2022-12-30", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-12-30_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "87acc5d75522b96b7ad4bf6ed798c404589dd00831599c11216433d928d32aa0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1662029824

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "209M"
zstd_bytes = 218863785

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221226"
previous_tag = "2022-12-26"
previous_file = "rust_riscv64_2022-12-26_03-05-rootfs.tar.zst"
previous_sha256 = "fe3670b96bf3b4c7c6a7c2ff2804aecc75afbd2b79c8e291cc094e10f5d01caa"

current_version = "latest02"
current_date = "20221230"
old_file = "rust_riscv64_2022-12-23_03-04-rootfs.tar.zst"
old_sha256 = "78e66bd17bdd1a204c72195542c619e52285cd8dbfc856bcd16c40f7a104637f"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-12-30_03-06-rootfs.tar.zst
# SHA256SUM=87acc5d75522b96b7ad4bf6ed798c404589dd00831599c11216433d928d32aa0
# BUILD_DATE=20221230
# BUILD_TAG=2022-12-30
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-30
begin = 2022-12-30 02:52:29.742224321+00:00
start-sync_0 = 03:00:20
start-zstd = 03:01:15
start-sync_1 = 03:05:57
end-sync_1 = 03:06:14
end = 2022-12-30 03:06:14.277791916+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-7) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.68.0-nightly (2381cbdb4 2022-12-23)'
rustc = 'rustc 1.68.0-nightly (ad8ae0504 2022-12-29)'
cc = 'cc (Debian 12.2.0-11) 12.2.0'
cargo_verbose = '''
cargo 1.68.0-nightly (2381cbdb4 2022-12-23)
release: 1.68.0-nightly
commit-hash: 2381cbdb4e9b07090f552d34a44a529b6e620e44
commit-date: 2022-12-23
host: riscv64gc-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.68.0-nightly (ad8ae0504 2022-12-29)
binary: rustc
commit-hash: ad8ae0504c54bc2bd8306abfcfe8546c1bb16a49
commit-date: 2022-12-29
host: riscv64gc-unknown-linux-gnu
release: 1.68.0-nightly
LLVM version: 15.0.6
'''
```
