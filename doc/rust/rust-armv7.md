# rust-armv7

## How to run it?

```sh
docker run \
    -it \
    --name rust-armv7 \
    cake233/rust-armv7
```

## How to exec shell?

```sh
docker exec -it rust-armv7 bash
```
<!-- repo=cake233/rust-armv7 -->

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
    cake233/rust-armv7 \
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
    cake233/rust-armv7 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-armv7.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-02-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-02-06_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ada8db7dcf200de793aea733fd70157a5e5b63e07b2d16753a0467e925a33c07"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1557317120

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "217M"
zstd_bytes = 227188363

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230203"
previous_tag = "2023-02-03"
previous_file = "rust_armhf_2023-02-03_03-04-rootfs.tar.zst"
previous_sha256 = "76ca30986188a305d17aba90efaa62d4c2aa14f4b2afbabe7525ece7bbb9441c"

current_version = "latest01"
current_date = "20230206"
old_file = "rust_armhf_2023-01-30_03-04-rootfs.tar.zst"
old_sha256 = "84e8dd209242638c4e3768b35a6f9569debc47f85d56cbd3776b69b77f4d1393"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-02-06_03-04-rootfs.tar.zst
# SHA256SUM=ada8db7dcf200de793aea733fd70157a5e5b63e07b2d16753a0467e925a33c07
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 02:52:27.601985770+00:00
start-sync_0 = 02:58:28
start-zstd = 02:59:27
start-sync_1 = 03:03:59
end-sync_1 = 03:04:18
end = 2023-02-06 03:04:18.735689379+00:00

[server]
repo = "cake233/rust-armv7"

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
cargo = 'cargo 1.69.0-nightly (e84a7928d 2023-01-31)'
rustc = 'rustc 1.69.0-nightly (75a0be98f 2023-02-05)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (e84a7928d 2023-01-31)
release: 1.69.0-nightly
commit-hash: e84a7928d93a31f284b497c214a2ece69b4d7719
commit-date: 2023-01-31
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (75a0be98f 2023-02-05)
binary: rustc
commit-hash: 75a0be98f25a4b9de5afa0e15eb016e7f9627032
commit-date: 2023-02-05
host: armv7-unknown-linux-gnueabihf
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
