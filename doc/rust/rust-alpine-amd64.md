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
tag = ["alpine", "2022-02-18", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-musl_amd64_2022-02-18_02-57.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "7c191373eb8b13047406b78cd6cf594542188ccb21551a7629cebd225a447785"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "770M"
tar_bytes = 806775296

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "173M"
zstd_bytes = 181329552

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220214"
previous_tag = "2022-02-14"
previous_file = "rust-musl_amd64_2022-02-14_02-55-rootfs.tar.zst"
previous_sha256 = "5dff031027a6cf4e282734d1e10dfe5a1406a34e7d65734ab594509ca5e3cdad"

current_version = "latest02"
current_date = "20220218"
old_file = "rust-musl_amd64_2022-02-11_02-56-rootfs.tar.zst"
old_sha256 = "7ffff7568bed2f90d8e3deb250637252e030f4245ec4329d5166512af306a011"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-02-18_02-57-rootfs.tar.zst
# SHA256SUM=7c191373eb8b13047406b78cd6cf594542188ccb21551a7629cebd225a447785
# BUILD_DATE=20220218
# BUILD_TAG=2022-02-18
# STATUS=completed
# VERSION=latest02
# END_TIME=02:57

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-18
begin = 2022-02-18 02:52:29.545498415+00:00
start-sync_0 = 02:53:23
start-zstd = 02:54:16
start-sync_1 = 02:56:54
end-sync_1 = 02:57:29
end = 2022-02-18 02:57:29.985023213+00:00

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
cargo = 'cargo 1.60.0-nightly (ea2a21c99 2022-02-15)'
rustc = 'rustc 1.60.0-nightly (30b3f35c4 2022-02-17)'
cc = 'cc (Alpine 11.2.1_git20220117) 11.2.1 20220117'
cargo_verbose = '''
cargo 1.60.0-nightly (ea2a21c99 2022-02-15)
release: 1.60.0-nightly
commit-hash: ea2a21c994ca1e4d4c49412827b3cf4dcb158b1d
commit-date: 2022-02-15
host: x86_64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (30b3f35c4 2022-02-17)
binary: rustc
commit-hash: 30b3f35c420694a4f24e5a4df00f06073f4f3a37
commit-date: 2022-02-17
host: x86_64-unknown-linux-musl
release: 1.60.0-nightly
LLVM version: 14.0.0
'''
```
