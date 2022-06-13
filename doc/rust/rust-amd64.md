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
tag = ["latest", "2022-06-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-06-13_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "646a3420b30bceb7a312282f6169a8092b6ad89072b8f8bacf23b4210748c60a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1580142592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "234M"
zstd_bytes = 244833818

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220610"
previous_tag = "2022-06-10"
previous_file = "rust_amd64_2022-06-10_03-02-rootfs.tar.zst"
previous_sha256 = "8ec005bf35fdcf391a0e406482a614fb7298eacf56af2833bb93d0eb7dd0a239"

current_version = "latest02"
current_date = "20220613"
old_file = "rust_amd64_2022-06-06_03-01-rootfs.tar.zst"
old_sha256 = "513f6e375bc0ce3b954abb700f99beb503824707fc162789ce2d5b5bcf58c77c"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-06-13_03-01-rootfs.tar.zst
# SHA256SUM=646a3420b30bceb7a312282f6169a8092b6ad89072b8f8bacf23b4210748c60a
# BUILD_DATE=20220613
# BUILD_TAG=2022-06-13
# STATUS=completed
# VERSION=latest02
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-13
begin = 2022-06-13 02:52:33.181943314+00:00
start-sync_0 = 02:54:18
start-zstd = 02:55:21
start-sync_1 = 03:01:36
end-sync_1 = 03:01:57
end = 2022-06-13 03:01:57.591065303+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (4d92f07f3 2022-06-09)'
rustc = 'rustc 1.63.0-nightly (546c826f0 2022-06-12)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (4d92f07f3 2022-06-09)
release: 1.63.0-nightly
commit-hash: 4d92f07f34ba7fb7d7f207564942508f46c225d3
commit-date: 2022-06-09
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (546c826f0 2022-06-12)
binary: rustc
commit-hash: 546c826f0ccaab36e897860205281f490db274e6
commit-date: 2022-06-12
host: x86_64-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.5
'''
```
