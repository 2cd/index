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
tag = ["latest", "2023-03-24", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2023-03-24_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "640c7eae7c0dcd9f92001282ffae26d9a1401f9bc7ab548c11be678e882fecb3"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1653130752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "193M"
zstd_bytes = 201417149

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230320"
previous_tag = "2023-03-20"
previous_file = "rust_mips64el_2023-03-20_03-06-rootfs.tar.zst"
previous_sha256 = "b3263dc3576564892db901a01681256bdf9ace1852bfbe99c746cd1a0db96ccb"

current_version = "latest01"
current_date = "20230324"
old_file = "rust_mips64el_2023-03-17_03-07-rootfs.tar.zst"
old_sha256 = "fa021c30ecaf4d34ce4087a426ef5861addcc562c693a347be8857070e72698f"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2023-03-24_03-06-rootfs.tar.zst
# SHA256SUM=640c7eae7c0dcd9f92001282ffae26d9a1401f9bc7ab548c11be678e882fecb3
# BUILD_DATE=20230324
# BUILD_TAG=2023-03-24
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-24
begin = 2023-03-24 02:52:35.371257809+00:00
start-sync_0 = 02:59:37
start-zstd = 03:00:47
start-sync_1 = 03:06:16
end-sync_1 = 03:06:37
end = 2023-03-24 03:06:37.298799060+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.70.0-nightly (15d090969 2023-03-21)'
rustc = 'rustc 1.70.0-nightly (1459b3128 2023-03-23)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.70.0-nightly (15d090969 2023-03-21)
release: 1.70.0-nightly
commit-hash: 15d090969743630bff549a1b068bcaa8174e5ee3
commit-date: 2023-03-21
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (1459b3128 2023-03-23)
binary: rustc
commit-hash: 1459b3128e288a85fcc4dd1fee7ada2cdcf28794
commit-date: 2023-03-23
host: mips64el-unknown-linux-gnuabi64
release: 1.70.0-nightly
LLVM version: 15.0.7
'''
```
