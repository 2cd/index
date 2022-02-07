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
tag = ["latest", "2022-02-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
x11_or_wayland = false

[file]
name = "rust_ppc64el_2022-02-07_03-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "706e1db0b1d67cc8f1fc5a61642dabbad6d167b1f13a9012b81fc98021aef706"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1676661760

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "226M"
zstd_bytes = 236607497

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220204"
previous_tag = "2022-02-04"
previous_file = "rust_ppc64el_2022-02-04_03-04-rootfs.tar.zst"
previous_sha256 = "46bcfc25f3f8a58c5d96dc2589d2c374d19eaec63682af35df6926a9990e234a"

current_version = "latest01"
current_date = "20220207"
old_file = "rust_ppc64el_2022-01-31_03-06-rootfs.tar.zst"
old_sha256 = "86e0163cd2040b697ae2d816978cf73a0434c97ba538feaa37cf8a7c9efb72dd"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-02-07_03-05-rootfs.tar.zst
# SHA256SUM=706e1db0b1d67cc8f1fc5a61642dabbad6d167b1f13a9012b81fc98021aef706
# BUILD_DATE=20220207
# BUILD_TAG=2022-02-07
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-07
begin = 2022-02-07 02:52:25.262456224+00:00
start-sync_0 = 02:59:23
start-zstd = 03:00:32
start-sync_1 = 03:05:29
end-sync_1 = 03:05:51
end = 2022-02-07 03:05:51.406816499+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-5) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.60.0-nightly (25fcb13 2022-02-01)'
rustc = 'rustc 1.60.0-nightly (f624427f8 2022-02-06)'
cc = 'cc (Debian 11.2.0-16) 11.2.0'
cargo_verbose = '''
cargo 1.60.0-nightly (25fcb13 2022-02-01)
release: 1.60.0-nightly
commit-hash: 25fcb135d02ea897ce894b67ae021f48107d522b
commit-date: 2022-02-01
host: powerpc64le-unknown-linux-gnu
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1l)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.60.0-nightly (f624427f8 2022-02-06)
binary: rustc
commit-hash: f624427f8771c00819684c783bb841bf72095704
commit-date: 2022-02-06
host: powerpc64le-unknown-linux-gnu
release: 1.60.0-nightly
LLVM version: 13.0.0
'''
```
