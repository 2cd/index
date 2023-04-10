# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-04-10", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-04-10_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0d2d0ab2c75e85b201011d7743edbb6ad5bafe38e4b46cf69690a8d477988cac"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1606599168

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 246920945

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230407"
previous_tag = "2023-04-07"
previous_file = "rust_amd64_2023-04-07_03-01-rootfs.tar.zst"
previous_sha256 = "3e3938125b588566dbdf1689fae8e9663ea98b55b08c863acb9f61d0b1dca839"

current_version = "latest02"
current_date = "20230410"
old_file = "rust_amd64_2023-04-03_03-01-rootfs.tar.zst"
old_sha256 = "cb08c1e1e4d1f4619be11b2c1e075e17a84a84e2e7bc0468733dbddafb3d2d4c"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-04-10_03-00-rootfs.tar.zst
# SHA256SUM=0d2d0ab2c75e85b201011d7743edbb6ad5bafe38e4b46cf69690a8d477988cac
# BUILD_DATE=20230410
# BUILD_TAG=2023-04-10
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-04-10
begin = 2023-04-10 02:52:30.141256159+00:00
start-sync_0 = 02:53:55
start-zstd = 02:54:58
start-sync_1 = 02:59:56
end-sync_1 = 03:00:18
end = 2023-04-10 03:00:18.932545759+00:00

[server]
repo = "cake233/rust-amd64"

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
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.70.0-nightly (0e474cfd7 2023-03-31)'
rustc = 'rustc 1.70.0-nightly (696aaad58 2023-04-09)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (0e474cfd7 2023-03-31)
release: 1.70.0-nightly
commit-hash: 0e474cfd7b16b018cf46e95da3f6a5b2f1f6a9e7
commit-date: 2023-03-31
host: x86_64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (696aaad58 2023-04-09)
binary: rustc
commit-hash: 696aaad58c57a589f6fb2ecff5bae2eec581cb71
commit-date: 2023-04-09
host: x86_64-unknown-linux-gnu
release: 1.70.0-nightly
LLVM version: 16.0.2
'''
```
