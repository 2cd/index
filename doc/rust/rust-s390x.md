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
tag = ["latest", "2022-01-31", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
x11_or_wayland = false

[file]
name = "rust_s390x_2022-01-31_03-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "1cc6d194382f66a09eb13334d5b5f38a582e6e968ea0ff8403b1fac17e372313"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1603398144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "219M"
zstd_bytes = 229265282

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220128"
previous_tag = "2022-01-28"
previous_file = "rust_s390x_2022-01-28_03-04-rootfs.tar.zst"
previous_sha256 = "e7f4ed3665193e60080c74383c0495aea63702cfb7c1242c1c149831e1d54d53"

current_version = "latest01"
current_date = "20220131"
old_file = "rust_s390x_2022-01-24_03-07-rootfs.tar.zst"
old_sha256 = "ecfa429d7ef5e71915a951af1e86ee7cc4e1c8bf8d9f4cb6f58ff03de48ee684"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-01-31_03-07-rootfs.tar.zst
# SHA256SUM=1cc6d194382f66a09eb13334d5b5f38a582e6e968ea0ff8403b1fac17e372313
# BUILD_DATE=20220131
# BUILD_TAG=2022-01-31
# STATUS=completed
# VERSION=latest01
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-31
begin = 2022-01-31 02:52:25.418243951+00:00
start-sync_0 = 02:59:47
start-zstd = 03:00:57
start-sync_1 = 03:06:42
end-sync_1 = 03:07:09
end = 2022-01-31 03:07:09.453795944+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-5) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.60.0-nightly (1c03475 2022-01-25)'
rustc = 'rustc 1.60.0-nightly (08df8b81d 2022-01-30)'
cc = 'cc (Debian 11.2.0-14) 11.2.0'
cargo_verbose = '''
cargo 1.60.0-nightly (1c03475 2022-01-25)
release: 1.60.0-nightly
commit-hash: 1c034752de0df744fcd7788fcbca158830b8bf85
commit-date: 2022-01-25
host: s390x-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (08df8b81d 2022-01-30)
binary: rustc
commit-hash: 08df8b81d6e723c66fee579d57d61dc60bc21fc1
commit-date: 2022-01-30
host: s390x-unknown-linux-gnu
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
