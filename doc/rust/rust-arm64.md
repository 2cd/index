# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-07-01", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-07-01_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0ad460b9fbe8bb10cf32ac1090d847525a6a344bc2894243b8d1830f1afc2164"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1821601280

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "258M"
zstd_bytes = 269518280

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "rust_arm64_2022-06-27_03-08-rootfs.tar.zst"
previous_sha256 = "a6d3d61d9ad623909323765f295cc2ad59f9d830236fec548362751d4f059ace"

current_version = "latest01"
current_date = "20220701"
old_file = "rust_arm64_2022-06-24_03-07-rootfs.tar.zst"
old_sha256 = "393f9a0f82fe9a09a0821f689b0f303a6df6c20abc356e6f12b402821b27a12b"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-07-01_03-09-rootfs.tar.zst
# SHA256SUM=0ad460b9fbe8bb10cf32ac1090d847525a6a344bc2894243b8d1830f1afc2164
# BUILD_DATE=20220701
# BUILD_TAG=2022-07-01
# STATUS=completed
# VERSION=latest01
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-01
begin = 2022-07-01 02:52:34.475249320+00:00
start-sync_0 = 03:00:23
start-zstd = 03:01:49
start-sync_1 = 03:08:42
end-sync_1 = 03:09:10
end = 2022-07-01 03:09:10.988246786+00:00

[server]
repo = "cake233/rust-arm64"

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
cargo = 'cargo 1.64.0-nightly (dbff32b27 2022-06-24)'
rustc = 'rustc 1.64.0-nightly (7425fb293 2022-06-30)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (dbff32b27 2022-06-24)
release: 1.64.0-nightly
commit-hash: dbff32b27893b899ae2397f3d56d1be111041d56
commit-date: 2022-06-24
host: aarch64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (7425fb293 2022-06-30)
binary: rustc
commit-hash: 7425fb293f510a6f138e82a963a3bc599a5b9e1c
commit-date: 2022-06-30
host: aarch64-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
