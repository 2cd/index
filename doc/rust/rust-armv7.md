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
tag = ["latest", "2024-02-26", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_armhf_2024-02-26_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "39a586db56ba83efb38d0449c7cb515990ddf3488fa2629619a5215e7977e524"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1551552512

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "226M"
zstd_bytes = 236589470

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_armhf_2023-11-27_03-02-rootfs.tar.zst"
previous_sha256 = "0fed4547656ffd8ba7829cb3754201131b84bb21d9852dfd826a3e5f7f445bf3"

current_version = "latest02"
current_date = "20240226"
old_file = "rust_armhf_2023-11-24_03-02-rootfs.tar.zst"
old_sha256 = "045c23aa187a1eb0db2ae0d392d33e253adfbb5eda7332c3ccf056a969e646a6"
# edition 2021
# DISTRO_NAME=rust_armhf
# ROOTFS_FILE=rust_armhf_2024-02-26_03-03-rootfs.tar.zst
# SHA256SUM=39a586db56ba83efb38d0449c7cb515990ddf3488fa2629619a5215e7977e524
# BUILD_DATE=20240226
# BUILD_TAG=2024-02-26
# STATUS=completed
# VERSION=latest02
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-26
begin = 2024-02-26 02:52:35.880911363+00:00
start-sync_0 = 02:58:08
start-zstd = 02:58:54
start-sync_1 = 03:02:48
end-sync_1 = 03:03:06
end = 2024-02-26 03:03:06.439247736+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.78.0-nightly (194a60b29 2024-02-21)'
rustc = 'rustc 1.78.0-nightly (0ecbd0605 2024-02-25)'
cc = 'cc (Debian 13.2.0-13) 13.2.0'
cargo_verbose = '''
cargo 1.78.0-nightly (194a60b29 2024-02-21)
release: 1.78.0-nightly
commit-hash: 194a60b2952bd5d12ba15dd2577a97eed7d3c587
commit-date: 2024-02-21
host: armv7-unknown-linux-gnueabihf
libgit2: 1.7.2 (sys:0.18.2 vendored)
libcurl: 8.6.0-DEV (sys:0.4.71+curl-8.6.0 vendored ssl:OpenSSL/3.2.1)
ssl: OpenSSL 3.2.1 30 Jan 2024
os: Linux [32-bit]
'''
rustc_verbose = '''
rustc 1.78.0-nightly (0ecbd0605 2024-02-25)
binary: rustc
commit-hash: 0ecbd0605770f45c9151715e66ba2b3cae367fcb
commit-date: 2024-02-25
host: armv7-unknown-linux-gnueabihf
release: 1.78.0-nightly
LLVM version: 18.1.0
'''
```
