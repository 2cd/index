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
tag = ["alpine", "2023-07-03", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-07-03_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7962e1042271e248c9997a5caf410cebed1ddd00c85317cdda77bb2689a417e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "867M"
tar_bytes = 908368896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "158M"
zstd_bytes = 165314260

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230630"
previous_tag = "2023-06-30"
previous_file = "rust-musl_arm64_2023-06-30_03-00-rootfs.tar.zst"
previous_sha256 = "f90a99eb1ef2e3b2a92b21ccf6c5d5e1e40c2471139b60df2eb757140a374664"

current_version = "latest01"
current_date = "20230703"
old_file = "rust-musl_arm64_2023-06-26_03-01-rootfs.tar.zst"
old_sha256 = "cb5c15d4bca22671b23e6a177042f14d535dd1d2d71e5f2daf47bab30590d8f7"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-07-03_03-02-rootfs.tar.zst
# SHA256SUM=a7962e1042271e248c9997a5caf410cebed1ddd00c85317cdda77bb2689a417e
# BUILD_DATE=20230703
# BUILD_TAG=2023-07-03
# STATUS=completed
# VERSION=latest01
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-03
begin = 2023-07-03 02:52:33.898738314+00:00
start-sync_0 = 02:56:38
start-zstd = 02:57:17
start-sync_1 = 03:01:59
end-sync_1 = 03:02:13
end = 2023-07-03 03:02:13.162396023+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (5b377cece 2023-06-30)'
rustc = 'rustc 1.72.0-nightly (839e9a6e1 2023-07-02)'
cc = 'cc (Alpine 13.1.1_git20230701) 13.1.1 20230701'
cargo_verbose = '''
cargo 1.72.0-nightly (5b377cece 2023-06-30)
release: 1.72.0-nightly
commit-hash: 5b377cece0e0dd0af686cf53ce4637d5d85c2a10
commit-date: 2023-06-30
host: aarch64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (839e9a6e1 2023-07-02)
binary: rustc
commit-hash: 839e9a6e1210934fd24b15548b811a97c77138fc
commit-date: 2023-07-02
host: aarch64-unknown-linux-musl
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
