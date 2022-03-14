# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-03-14", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
x11_or_wayland = false

[file]
name = "rust_s390x_2022-03-14_03-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "9e24765c155ca92bb3e436cc209adda3044f1c31f1608cbd8d2e5ea776df1dce"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1718914048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "243M"
zstd_bytes = 254564752

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220311"
previous_tag = "2022-03-11"
previous_file = "rust_s390x_2022-03-11_03-08-rootfs.tar.zst"
previous_sha256 = "b113631af94e6c3c58b57c3be740cfaa46c26e1faad4a30dd099ec842513880e"

current_version = "latest02"
current_date = "20220314"
old_file = "rust_s390x_2022-03-07_03-06-rootfs.tar.zst"
old_sha256 = "949749a07d531bfc54dfde0397b048c20a91cef553e87ad222ac55b43d26d736"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-03-14_03-06-rootfs.tar.zst
# SHA256SUM=9e24765c155ca92bb3e436cc209adda3044f1c31f1608cbd8d2e5ea776df1dce
# BUILD_DATE=20220314
# BUILD_TAG=2022-03-14
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-14
begin = 2022-03-14 02:52:25.690964355+00:00
start-sync_0 = 02:59:06
start-zstd = 03:00:11
start-sync_1 = 03:05:44
end-sync_1 = 03:06:06
end = 2022-03-14 03:06:06.300281441+00:00

[server]
repo = "cake233/rust-s390x"

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
cargo = 'cargo 1.61.0-nightly (65c826642 2022-03-09)'
rustc = 'rustc 1.61.0-nightly (e95b10ba4 2022-03-13)'
cc = 'cc (Debian 11.2.0-18) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (65c826642 2022-03-09)
release: 1.61.0-nightly
commit-hash: 65c82664263feddc5fe2d424be0993c28d46377a
commit-date: 2022-03-09
host: s390x-unknown-linux-gnu
libgit2: 1.4.1 (sys:0.14.1 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (e95b10ba4 2022-03-13)
binary: rustc
commit-hash: e95b10ba4ac4564ed25f7eef143e3182c33b3902
commit-date: 2022-03-13
host: s390x-unknown-linux-gnu
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
