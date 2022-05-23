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
tag = ["latest", "2022-05-23", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2022-05-23_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8032ae74d45a83c759b6c33da32745274045989b131d2a5be7eed5dae5242790"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1580838912

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "233M"
zstd_bytes = 243784392

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220520"
previous_tag = "2022-05-20"
previous_file = "rust_amd64_2022-05-20_03-00-rootfs.tar.zst"
previous_sha256 = "c1e19938e9ef20d01508f57f39a3009a4f7e228720f9be7330aeb85929872fff"

current_version = "latest02"
current_date = "20220523"
old_file = "rust_amd64_2022-05-16_03-02-rootfs.tar.zst"
old_sha256 = "83866cf135319c0e4829ae9fadee2f5b008661a2b8a5acd1d4653b3d75a1f726"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2022-05-23_03-00-rootfs.tar.zst
# SHA256SUM=8032ae74d45a83c759b6c33da32745274045989b131d2a5be7eed5dae5242790
# BUILD_DATE=20220523
# BUILD_TAG=2022-05-23
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-23
begin = 2022-05-23 02:52:37.226667469+00:00
start-sync_0 = 02:54:00
start-zstd = 02:54:58
start-sync_1 = 02:59:56
end-sync_1 = 03:00:19
end = 2022-05-23 03:00:19.533014169+00:00

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
cargo = 'cargo 1.63.0-nightly (a4c1cd0eb 2022-05-18)'
rustc = 'rustc 1.63.0-nightly (b2eed72a6 2022-05-22)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (a4c1cd0eb 2022-05-18)
release: 1.63.0-nightly
commit-hash: a4c1cd0eb6b18082a7e693f5a665548fe1534be4
commit-date: 2022-05-18
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: OracleLinux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (b2eed72a6 2022-05-22)
binary: rustc
commit-hash: b2eed72a6fbf254e7d44942eaa121fcbed05d3fb
commit-date: 2022-05-22
host: x86_64-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.4
'''
```
