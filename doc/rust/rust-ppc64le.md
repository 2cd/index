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
tag = ["latest", "2023-06-09", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2023-06-09_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "58c8c7efcbc2a11933ce4fcc91a4f0b66560e2006f6f6a9914764044aac4b03c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1647151104

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "216M"
zstd_bytes = 226471581

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230605"
previous_tag = "2023-06-05"
previous_file = "rust_ppc64el_2023-06-05_03-05-rootfs.tar.zst"
previous_sha256 = "5b3903f4417cf9cbb0c14bfa2b804eec54aabe80b8c7c62c80479e8c70964d8b"

current_version = "latest02"
current_date = "20230609"
old_file = "rust_ppc64el_2023-06-02_03-05-rootfs.tar.zst"
old_sha256 = "fb62f683d2c7b09b0c0808d389916d62ade8fbfeae2b2d9db47ef441a2d6a076"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2023-06-09_03-09-rootfs.tar.zst
# SHA256SUM=58c8c7efcbc2a11933ce4fcc91a4f0b66560e2006f6f6a9914764044aac4b03c
# BUILD_DATE=20230609
# BUILD_TAG=2023-06-09
# STATUS=completed
# VERSION=latest02
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-06-09
begin = 2023-06-09 02:52:39.947047748+00:00
start-sync_0 = 03:01:15
start-zstd = 03:02:31
start-sync_1 = 03:09:25
end-sync_1 = 03:09:50
end = 2023-06-09 03:09:50.523588947+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-9) 2.36'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (b0fa79679 2023-06-03)'
rustc = 'rustc 1.72.0-nightly (8b35c0bb0 2023-06-08)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.72.0-nightly (b0fa79679 2023-06-03)
release: 1.72.0-nightly
commit-hash: b0fa79679e717cd077b7fc0fa4166f47107f1ba9
commit-date: 2023-06-03
host: powerpc64le-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.1 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1t)
ssl: OpenSSL 1.1.1t  7 Feb 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (8b35c0bb0 2023-06-08)
binary: rustc
commit-hash: 8b35c0bb0f833c0077dc57006eb317edde2a2d1e
commit-date: 2023-06-08
host: powerpc64le-unknown-linux-gnu
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
