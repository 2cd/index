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
tag = ["latest", "2022-05-20", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-05-20_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0ae1852acf8c0c7ae4b923e7931758a54b90f5c10cffea1f951eff1becfa0f13"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1667121664

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "209M"
zstd_bytes = 218746602

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220516"
previous_tag = "2022-05-16"
previous_file = "rust_mips64el_2022-05-16_03-05-rootfs.tar.zst"
previous_sha256 = "4190c297975ea597f639e1d1ceb74c5d71ef10a64fd27ab98dc61914b238b445"

current_version = "latest01"
current_date = "20220520"
old_file = "rust_mips64el_2022-05-13_03-07-rootfs.tar.zst"
old_sha256 = "9c1d7c576b459eb55c504efa72a6a83c8bcb23550faa628cf8e041da916ed636"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-05-20_03-10-rootfs.tar.zst
# SHA256SUM=0ae1852acf8c0c7ae4b923e7931758a54b90f5c10cffea1f951eff1becfa0f13
# BUILD_DATE=20220520
# BUILD_TAG=2022-05-20
# STATUS=completed
# VERSION=latest01
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-20
begin = 2022-05-20 02:52:29.356276030+00:00
start-sync_0 = 03:01:53
start-zstd = 03:03:09
start-sync_1 = 03:10:04
end-sync_1 = 03:10:28
end = 2022-05-20 03:10:28.152379875+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (a4c1cd0eb 2022-05-18)'
rustc = 'rustc 1.63.0-nightly (c06728704 2022-05-19)'
cc = 'cc (Debian 11.3.0-1) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (a4c1cd0eb 2022-05-18)
release: 1.63.0-nightly
commit-hash: a4c1cd0eb6b18082a7e693f5a665548fe1534be4
commit-date: 2022-05-18
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (c06728704 2022-05-19)
binary: rustc
commit-hash: c0672870491e84362f76ddecd50fa229f9b06dff
commit-date: 2022-05-19
host: mips64el-unknown-linux-gnuabi64
release: 1.63.0-nightly
LLVM version: 14.0.4
'''
```
