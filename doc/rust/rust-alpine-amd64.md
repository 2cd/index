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
tag = ["alpine", "2022-05-02", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-05-02_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6d954d7f6a2b66fe81170f069f70e9e8b4af2a9d6ce91a91827364200a16e24e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "745M"
tar_bytes = 780922368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "152M"
zstd_bytes = 158791915

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220429"
previous_tag = "2022-04-29"
previous_file = "rust-musl_amd64_2022-04-29_03-00-rootfs.tar.zst"
previous_sha256 = "0a2dc1ff0791a6cd66c2f33462424af30156eb0e9769a0b125a59cbfd1c6701b"

current_version = "latest02"
current_date = "20220502"
old_file = "rust-musl_amd64_2022-04-25_02-59-rootfs.tar.zst"
old_sha256 = "5ceb97d01b554c3cab1b20b28e5bb9116a4f3ba88b2a5e2b59eaac1df145c3a2"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-05-02_02-59-rootfs.tar.zst
# SHA256SUM=6d954d7f6a2b66fe81170f069f70e9e8b4af2a9d6ce91a91827364200a16e24e
# BUILD_DATE=20220502
# BUILD_TAG=2022-05-02
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-02
begin = 2022-05-02 02:52:25.581873104+00:00
start-sync_0 = 02:53:04
start-zstd = 02:53:41
start-sync_1 = 02:58:54
end-sync_1 = 02:59:08
end = 2022-05-02 02:59:08.644595666+00:00

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.62.0-nightly (f63f23ff1 2022-04-28)'
rustc = 'rustc 1.62.0-nightly (4dd8b420c 2022-05-01)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.62.0-nightly (f63f23ff1 2022-04-28)
release: 1.62.0-nightly
commit-hash: f63f23ff1f1a12ede8585bbd1bbf0c536e50293d
commit-date: 2022-04-28
host: x86_64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (4dd8b420c 2022-05-01)
binary: rustc
commit-hash: 4dd8b420c027001e47b0d811a7e55e2fe1de1395
commit-date: 2022-05-01
host: x86_64-unknown-linux-musl
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
