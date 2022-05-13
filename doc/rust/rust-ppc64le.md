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
tag = ["latest", "2022-05-13", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-05-13_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "872be13ff13a693cc6664866a2586a721ed12a88b36ad79b7f13358dfbca0ed2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1719047680

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "230M"
zstd_bytes = 240792400

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220506"
previous_tag = "2022-05-06"
previous_file = "rust_ppc64el_2022-05-06_03-05-rootfs.tar.zst"
previous_sha256 = "dcfadadce8e68bbc33b9be5e1a50fce7e7a31b5528c1f7c1e1e9ace412039e55"

current_version = "latest01"
current_date = "20220513"
old_file = "rust_ppc64el_2022-05-02_03-05-rootfs.tar.zst"
old_sha256 = "8e1a5b42b9e2a370de3d143e271726640511bac4c1ba74066e14013cea3c648e"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-05-13_03-05-rootfs.tar.zst
# SHA256SUM=872be13ff13a693cc6664866a2586a721ed12a88b36ad79b7f13358dfbca0ed2
# BUILD_DATE=20220513
# BUILD_TAG=2022-05-13
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-13
begin = 2022-05-13 02:52:39.956416685+00:00
start-sync_0 = 02:58:47
start-zstd = 02:59:49
start-sync_1 = 03:04:53
end-sync_1 = 03:05:12
end = 2022-05-13 03:05:12.138919681+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.62.0-nightly (3f052d8ee 2022-05-12)'
rustc = 'rustc 1.62.0-nightly (a5ad0d29a 2022-05-12)'
cc = 'cc (Debian 11.3.0-1) 11.3.0'
cargo_verbose = '''
cargo 1.62.0-nightly (3f052d8ee 2022-05-12)
release: 1.62.0-nightly
commit-hash: 3f052d8eed98c6a24f8b332fb2e6e6249d12d8c1
commit-date: 2022-05-12
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (a5ad0d29a 2022-05-12)
binary: rustc
commit-hash: a5ad0d29a401007b51715852cc702e441ac2248c
commit-date: 2022-05-12
host: powerpc64le-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
