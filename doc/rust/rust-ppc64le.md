# rust-ppc64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```sh
docker exec -it rust-ppc64le bash
```
<!-- repo=cake233/rust-ppc64le -->

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
    cake233/rust-ppc64le \
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
    cake233/rust-ppc64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-08-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-08-25_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b9dcdfe3542d3b88607e9e8c841e5ac8badb29d4e95b2f1e026f40d14775d685"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1750430720

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 225763834

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230821"
previous_tag = "2023-08-21"
previous_file = "rust_ppc64el_2023-08-21_03-07-rootfs.tar.zst"
previous_sha256 = "19059a2d3ba0f513d434354ef58e6e67ab78d72a490eb6012543d52ac5583c81"

current_version = "latest01"
current_date = "20230825"
old_file = "rust_ppc64el_2023-08-18_03-05-rootfs.tar.zst"
old_sha256 = "688cea13e87d495d7af9902f6289325f223ea4440f356a0e7a7a149545e80201"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-08-25_03-06-rootfs.tar.zst
# SHA256SUM=b9dcdfe3542d3b88607e9e8c841e5ac8badb29d4e95b2f1e026f40d14775d685
# BUILD_DATE=20230825
# BUILD_TAG=2023-08-25
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-08-25
begin = 2023-08-25 02:52:33.163167443+00:00
start-sync_0 = 02:59:17
start-zstd = 03:00:20
start-sync_1 = 03:05:59
end-sync_1 = 03:06:23
end = 2023-08-25 03:06:23.497807858+00:00

[server]
repo = "cake233/rust-ppc64le"

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
ldd = 'ldd (Debian GLIBC 2.37-7) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.74.0-nightly (2cc50bc0b 2023-08-22)'
rustc = 'rustc 1.74.0-nightly (58eefc33a 2023-08-24)'
cc = 'cc (Debian 13.2.0-2) 13.2.0'
cargo_verbose = '''
cargo 1.74.0-nightly (2cc50bc0b 2023-08-22)
release: 1.74.0-nightly
commit-hash: 2cc50bc0b63ad20da193e002ba11d391af0104b7
commit-date: 2023-08-22
host: powerpc64le-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.2.1-DEV (sys:0.4.65+curl-8.2.1 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.74.0-nightly (58eefc33a 2023-08-24)
binary: rustc
commit-hash: 58eefc33adf769a1abe12ad94b3e6811185b4ce5
commit-date: 2023-08-24
host: powerpc64le-unknown-linux-gnu
release: 1.74.0-nightly
LLVM version: 17.0.0
'''
```
