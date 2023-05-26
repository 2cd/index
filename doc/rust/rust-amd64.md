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
tag = ["latest", "2023-05-26", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-05-26_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5dbe67e0f5ebd1a217599fa6941479615d3368dc39a7295b97006610b8fcf56f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1594221056

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "236M"
zstd_bytes = 247212689

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230522"
previous_tag = "2023-05-22"
previous_file = "rust_amd64_2023-05-22_02-59-rootfs.tar.zst"
previous_sha256 = "bef1aad8a4484a8c6ffa97e957ae9ede23a3c774aa209becfe5353b8e9ea07ad"

current_version = "latest01"
current_date = "20230526"
old_file = "rust_amd64_2023-05-19_03-01-rootfs.tar.zst"
old_sha256 = "c3c324d50b99c0d72f66d9e64782dc9cb9dfec8d1a18cb6dee5919d8d324340a"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-05-26_03-00-rootfs.tar.zst
# SHA256SUM=5dbe67e0f5ebd1a217599fa6941479615d3368dc39a7295b97006610b8fcf56f
# BUILD_DATE=20230526
# BUILD_TAG=2023-05-26
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-26
begin = 2023-05-26 02:52:30.029225735+00:00
start-sync_0 = 02:54:10
start-zstd = 02:55:15
start-sync_1 = 03:00:33
end-sync_1 = 03:00:55
end = 2023-05-26 03:00:55.092250958+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.71.0-nightly (64fb38c97 2023-05-23)'
rustc = 'rustc 1.71.0-nightly (a2b1646c5 2023-05-25)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.71.0-nightly (64fb38c97 2023-05-23)
release: 1.71.0-nightly
commit-hash: 64fb38c97ac4d3a327fc9032c862dd28c8833b17
commit-date: 2023-05-23
host: x86_64-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Debian 12.0.0 [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (a2b1646c5 2023-05-25)
binary: rustc
commit-hash: a2b1646c597329d0a25efa3889b66650f65de1de
commit-date: 2023-05-25
host: x86_64-unknown-linux-gnu
release: 1.71.0-nightly
LLVM version: 16.0.4
'''
```
