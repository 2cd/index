# rust-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-amd64 bash
```
<!-- repo=cake233/rust-alpine-amd64 -->

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
    cake233/rust-alpine-amd64 \
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
    cake233/rust-alpine-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2021-12-27", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-musl_amd64_2021-12-27_03-00.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "69c675351286b2a2f67973f057e683ce26c47f6731762d4314c8ba2010f67d4b"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "833M"
tar_bytes = 872450560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198469363

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211224"
previous_tag = "2021-12-24"
previous_file = "rust-musl_amd64_2021-12-24_02-56-rootfs.tar.zst"
previous_sha256 = "720ee4648eb8ae5cb7797ccd20ec95b5615adce542f9f9374796938438a772bb"

current_version = "latest01"
current_date = "20211227"
old_file = "rust-musl_amd64_2021-12-20_02-56-rootfs.tar.zst"
old_sha256 = "87800f14a81ff111ebc7ed7a2d4e0d3ac7828da2a7f68de8bab3096369abe67a"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2021-12-27_03-00-rootfs.tar.zst
# SHA256SUM=69c675351286b2a2f67973f057e683ce26c47f6731762d4314c8ba2010f67d4b
# BUILD_DATE=20211227
# BUILD_TAG=2021-12-27
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-27
begin = 2021-12-27 02:55:51.441698203+00:00
start-sync_0 = 02:56:34
start-zstd = 02:57:23
start-sync_1 = 02:59:52
end-sync_1 = 03:00:10
end = 2021-12-27 03:00:10.657346421+00:00

[server]
repo = "cake233/rust-alpine-amd64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (x86_64) Version 1.2.2'
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.59.0-nightly (fcef61230 2021-12-17)'
rustc = 'rustc 1.59.0-nightly (f8abed9ed 2021-12-26)'
cc = 'cc (Alpine 11.2.1_git20211128) 11.2.1 20211128'
cargo_verbose = '''
cargo 1.59.0-nightly (fcef61230 2021-12-17)
release: 1.59.0-nightly
commit-hash: fcef61230c3b6213b6b0d233a36ba4ebd1649ec3
commit-date: 2021-12-17
host: x86_64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.59.0-nightly (f8abed9ed 2021-12-26)
binary: rustc
commit-hash: f8abed9ed48bace6be0087bcd44ed534e239b8d8
commit-date: 2021-12-26
host: x86_64-unknown-linux-musl
release: 1.59.0-nightly
LLVM version: 13.0.0
'''
```
