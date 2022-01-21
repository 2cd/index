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
tag = ["latest", "2022-01-21", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "rust_armhf_2022-01-21_03-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "a595320a01888f03f421b618fd30915ae4c62970679278167dfb9611910999c4"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.4G"
tar_bytes = 1490114560

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "229M"
zstd_bytes = 239865736

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220121"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2022-01-21_03-06-rootfs.tar.zst
# SHA256SUM=a595320a01888f03f421b618fd30915ae4c62970679278167dfb9611910999c4
# BUILD_DATE=20220121
# BUILD_TAG=2022-01-21
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-21
begin = 2022-01-21 02:52:25.834148308+00:00
start-sync_0 = 03:00:20
start-zstd = 03:01:25
start-sync_1 = 03:06:24
end-sync_1 = 03:06:53
end = 2022-01-21 03:06:53.565056209+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-3) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.60.0-nightly (95bb3c92b 2022-01-18)'
rustc = 'rustc 1.60.0-nightly (777bb86bc 2022-01-20)'
cc = 'cc (Debian 11.2.0-14) 11.2.0'
cargo_verbose = '''
cargo 1.60.0-nightly (95bb3c92b 2022-01-18)
release: 1.60.0-nightly
commit-hash: 95bb3c92bf516017e812e7f1c14c2dea3845b30e
commit-date: 2022-01-18
host: armv7-unknown-linux-gnueabihf
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (777bb86bc 2022-01-20)
binary: rustc
commit-hash: 777bb86bcdbc568be7cff6eeeaaf81a89b4aa50b
commit-date: 2022-01-20
host: armv7-unknown-linux-gnueabihf
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
