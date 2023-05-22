# rust-mips64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```sh
docker exec -it rust-mips64le bash
```
<!-- repo=cake233/rust-mips64le -->

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
    cake233/rust-mips64le \
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
    cake233/rust-mips64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-05-22", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2023-05-22_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b24ba772f965db28e9baff74e06b67521cf9d13e3cdb15fc925f3ade142c5526"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1640431616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "193M"
zstd_bytes = 201773922

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230519"
previous_tag = "2023-05-19"
previous_file = "rust_mips64el_2023-05-19_03-05-rootfs.tar.zst"
previous_sha256 = "9250096b7f90f29169654fd88f5e9fa5284426acb616731497200335c9220906"

current_version = "latest02"
current_date = "20230522"
old_file = "rust_mips64el_2023-05-15_03-04-rootfs.tar.zst"
old_sha256 = "1fa2068bf740a1acbde3bcc16da97e27b6403fbc49017c50c551d9756f6e91aa"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2023-05-22_03-04-rootfs.tar.zst
# SHA256SUM=b24ba772f965db28e9baff74e06b67521cf9d13e3cdb15fc925f3ade142c5526
# BUILD_DATE=20230522
# BUILD_TAG=2023-05-22
# STATUS=completed
# VERSION=latest02
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-22
begin = 2023-05-22 02:52:31.093241280+00:00
start-sync_0 = 02:58:27
start-zstd = 02:59:22
start-sync_1 = 03:04:29
end-sync_1 = 03:04:45
end = 2023-05-22 03:04:45.064685755+00:00

[server]
repo = "cake233/rust-mips64le"

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.71.0-nightly (09276c703 2023-05-16)'
rustc = 'rustc 1.71.0-nightly (9d871b061 2023-05-21)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.71.0-nightly (09276c703 2023-05-16)
release: 1.71.0-nightly
commit-hash: 09276c703a473ab33daaeb94917232e80eefd628
commit-date: 2023-05-16
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.71.0-nightly (9d871b061 2023-05-21)
binary: rustc
commit-hash: 9d871b0617a4b3d6610b7cee0ab5310dcb542c62
commit-date: 2023-05-21
host: mips64el-unknown-linux-gnuabi64
release: 1.71.0-nightly
LLVM version: 16.0.4
'''
```
