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
tag = ["latest", "2023-11-27", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-11-27_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b1ada3fb2e8f52a1963baf5be5bff055e54e7ab0805baa0a309c6b77a9998b55"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1768164352

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "219M"
zstd_bytes = 228727656

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231124"
previous_tag = "2023-11-24"
previous_file = "rust_ppc64el_2023-11-24_03-02-rootfs.tar.zst"
previous_sha256 = "a81223bcdb5870598ca1c4a4db2222404549b763a08f7760e1ccfc21edd1917b"

current_version = "latest01"
current_date = "20231127"
old_file = "rust_ppc64el_2023-11-20_03-03-rootfs.tar.zst"
old_sha256 = "c1d24b8ee648a7c83df4f92375fe234771334da4e87d0b95c76190723de1f0c3"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-11-27_03-02-rootfs.tar.zst
# SHA256SUM=b1ada3fb2e8f52a1963baf5be5bff055e54e7ab0805baa0a309c6b77a9998b55
# BUILD_DATE=20231127
# BUILD_TAG=2023-11-27
# STATUS=completed
# VERSION=latest01
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-27
begin = 2023-11-27 02:52:32.112451138+00:00
start-sync_0 = 02:57:17
start-zstd = 02:58:04
start-sync_1 = 03:02:21
end-sync_1 = 03:02:35
end = 2023-11-27 03:02:35.281400916+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.76.0-nightly (9b13310ca 2023-11-24)'
rustc = 'rustc 1.76.0-nightly (6cf088810 2023-11-26)'
cc = 'cc (Debian 13.2.0-7) 13.2.0'
cargo_verbose = '''
cargo 1.76.0-nightly (9b13310ca 2023-11-24)
release: 1.76.0-nightly
commit-hash: 9b13310ca596020a737aaa47daa4ed9ff8898a2f
commit-date: 2023-11-24
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.76.0-nightly (6cf088810 2023-11-26)
binary: rustc
commit-hash: 6cf088810f66fff15d05bf7135c5f5888b7c93b4
commit-date: 2023-11-26
host: powerpc64le-unknown-linux-gnu
release: 1.76.0-nightly
LLVM version: 17.0.5
'''
```
