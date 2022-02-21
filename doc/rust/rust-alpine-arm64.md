# rust-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-arm64 bash
```
<!-- repo=cake233/rust-alpine-arm64 -->

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
    cake233/rust-alpine-arm64 \
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
    cake233/rust-alpine-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2022-02-21", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "rust-musl_arm64_2022-02-21_02-57.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "e6d9acd0fa09ef99a49afb17ec0277eb745319cf57997cff1bd6dc1b08ab18df"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "720M"
tar_bytes = 754950144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "167M"
zstd_bytes = 174696993

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220218"
previous_tag = "2022-02-18"
previous_file = "rust-musl_arm64_2022-02-18_02-57-rootfs.tar.zst"
previous_sha256 = "6a76fb658e5735ae8c9176955da73ecb101044b2f281204c08b46946b8a1855c"

current_version = "latest01"
current_date = "20220221"
old_file = "rust-musl_arm64_2022-02-14_02-58-rootfs.tar.zst"
old_sha256 = "5669d33864ac3b6286999d308dce31c2c3425e342b2c1f496e11fbe62cc093cf"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-02-21_02-57-rootfs.tar.zst
# SHA256SUM=e6d9acd0fa09ef99a49afb17ec0277eb745319cf57997cff1bd6dc1b08ab18df
# BUILD_DATE=20220221
# BUILD_TAG=2022-02-21
# STATUS=completed
# VERSION=latest01
# END_TIME=02:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-21
begin = 2022-02-21 02:52:23.038249939+00:00
start-sync_0 = 02:54:08
start-zstd = 02:54:48
start-sync_1 = 02:56:45
end-sync_1 = 02:57:08
end = 2022-02-21 02:57:08.194678100+00:00

[server]
repo = "cake233/rust-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.2'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (ea2a21c99 2022-02-15)'
rustc = 'rustc 1.61.0-nightly (45e2c2881 2022-02-20)'
cc = 'cc (Alpine 11.2.1_git20220117) 11.2.1 20220117'
cargo_verbose = '''
cargo 1.61.0-nightly (ea2a21c99 2022-02-15)
release: 1.61.0-nightly
commit-hash: ea2a21c994ca1e4d4c49412827b3cf4dcb158b1d
commit-date: 2022-02-15
host: aarch64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (45e2c2881 2022-02-20)
binary: rustc
commit-hash: 45e2c2881d11324d610815bfff097e25c412199e
commit-date: 2022-02-20
host: aarch64-unknown-linux-musl
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
