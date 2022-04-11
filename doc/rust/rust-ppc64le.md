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
tag = ["latest", "2022-04-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
x11_or_wayland = false

[file]
name = "rust_ppc64el_2022-04-11_02-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "24944432e994c15d23c4276be512b21ef532a95313d8714655385812be9b008a"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1725870080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "234M"
zstd_bytes = 244904753

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220408"
previous_tag = "2022-04-08"
previous_file = "rust_ppc64el_2022-04-08_03-46-rootfs.tar.zst"
previous_sha256 = "38cd417bd4d3f08e07db9a4494818f1820e8b08d9d83590b7c4ce44f16f9f5f0"

current_version = "latest01"
current_date = "20220411"
old_file = "rust_ppc64el_2022-04-04_02-06-rootfs.tar.zst"
old_sha256 = "61853b25fe101354e915c5c4c77994a3f05d494946529490632ffeee2658db6b"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-04-11_02-05-rootfs.tar.zst
# SHA256SUM=24944432e994c15d23c4276be512b21ef532a95313d8714655385812be9b008a
# BUILD_DATE=20220411
# BUILD_TAG=2022-04-11
# STATUS=completed
# VERSION=latest01
# END_TIME=02:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-11
begin = 2022-04-11 01:52:27.915218302+00:00
start-sync_0 = 01:58:54
start-zstd = 01:59:55
start-sync_1 = 02:05:20
end-sync_1 = 02:05:41
end = 2022-04-11 02:05:41.155280558+00:00

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
cargo = 'cargo 1.62.0-nightly (e2e2ddd 2022-04-05)'
rustc = 'rustc 1.62.0-nightly (1f7fb6413 2022-04-10)'
cc = 'cc (Debian 11.2.0-19) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (e2e2ddd 2022-04-05)
release: 1.62.0-nightly
commit-hash: e2e2dddebe66dfc1403a312653557e332445308b
commit-date: 2022-04-05
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (1f7fb6413 2022-04-10)
binary: rustc
commit-hash: 1f7fb6413d6d6c0c929b223e478e44c3db991b03
commit-date: 2022-04-10
host: powerpc64le-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.0
'''
```
