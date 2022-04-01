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
tag = ["latest", "2022-04-01", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2022-04-01_02-03.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f85f96d7160b26e24bfdc6e07487d3284da5aab6fd3150258b5a23618c7059d3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1516343808

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "233M"
zstd_bytes = 243759996

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "rust_armhf_2022-03-28_02-04-rootfs.tar.zst"
previous_sha256 = "55acda83cdc1dfe94299b9b76a89d6e0e699bf766bee94bfb2072f8afe4cbcb7"

current_version = "latest01"
current_date = "20220401"
old_file = "rust_armhf_2022-03-25_03-04-rootfs.tar.zst"
old_sha256 = "b0969040d53c2326cc3b316f7e6483911854752e3f5913a6ac422d97ba8de7c3"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-04-01_02-03-rootfs.tar.zst
# SHA256SUM=f85f96d7160b26e24bfdc6e07487d3284da5aab6fd3150258b5a23618c7059d3
# BUILD_DATE=20220401
# BUILD_TAG=2022-04-01
# STATUS=completed
# VERSION=latest01
# END_TIME=02:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-01
begin = 2022-04-01 01:52:24.003430668+00:00
start-sync_0 = 01:57:57
start-zstd = 01:58:50
start-sync_1 = 02:03:03
end-sync_1 = 02:03:22
end = 2022-04-01 02:03:22.261909079+00:00

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.61.0-nightly (1ef1e0a12 2022-03-31)'
rustc = 'rustc 1.61.0-nightly (0677edc86 2022-03-31)'
cc = 'cc (Debian 11.2.0-19) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (1ef1e0a12 2022-03-31)
release: 1.61.0-nightly
commit-hash: 1ef1e0a12723ce9548d7da2b63119de9002bead8
commit-date: 2022-03-31
host: armv7-unknown-linux-gnueabihf
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (0677edc86 2022-03-31)
binary: rustc
commit-hash: 0677edc86e342f333d4828b0ee1ef395a4e70fe5
commit-date: 2022-03-31
host: armv7-unknown-linux-gnueabihf
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
