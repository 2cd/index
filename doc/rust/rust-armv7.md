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
tag = ["latest", "2023-03-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2023-03-03_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3bb42641b17a53b0661a51517bd3394f1219a9c795b8e7be048b4a5007c7abc8"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1537951744

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "215M"
zstd_bytes = 224756007

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230227"
previous_tag = "2023-02-27"
previous_file = "rust_armhf_2023-02-27_03-06-rootfs.tar.zst"
previous_sha256 = "e2d2545e7fe15c59021ca3993c0d04cf36ccf7572b6815f6852ee41b2edffb98"

current_version = "latest01"
current_date = "20230303"
old_file = "rust_armhf_2023-02-24_03-03-rootfs.tar.zst"
old_sha256 = "6587a1bd888462e9d4345b9f849a9ea4e736de3e5a675668497df9d80de7cd7a"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2023-03-03_03-05-rootfs.tar.zst
# SHA256SUM=3bb42641b17a53b0661a51517bd3394f1219a9c795b8e7be048b4a5007c7abc8
# BUILD_DATE=20230303
# BUILD_TAG=2023-03-03
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-03
begin = 2023-03-03 02:52:27.315605060+00:00
start-sync_0 = 02:59:05
start-zstd = 03:00:12
start-sync_1 = 03:05:32
end-sync_1 = 03:05:54
end = 2023-03-03 03:05:54.066756054+00:00

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
cargo = 'cargo 1.69.0-nightly (9880b408a 2023-02-28)'
rustc = 'rustc 1.69.0-nightly (13471d3b2 2023-03-02)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (9880b408a 2023-02-28)
release: 1.69.0-nightly
commit-hash: 9880b408a3af50c08fab3dbf4aa2a972df71e951
commit-date: 2023-02-28
host: armv7-unknown-linux-gnueabihf
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (13471d3b2 2023-03-02)
binary: rustc
commit-hash: 13471d3b2046cce78181dde6cfc146c09f55e29e
commit-date: 2023-03-02
host: armv7-unknown-linux-gnueabihf
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
