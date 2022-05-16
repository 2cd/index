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
tag = ["latest", "2022-05-16", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-05-16_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c6c5ceeffe03ef165aaf86ea6a889e56e1288cf51d785cd638e258c7f8de1fd2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1724395520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "232M"
zstd_bytes = 242452867

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220513"
previous_tag = "2022-05-13"
previous_file = "rust_ppc64el_2022-05-13_03-05-rootfs.tar.zst"
previous_sha256 = "872be13ff13a693cc6664866a2586a721ed12a88b36ad79b7f13358dfbca0ed2"

current_version = "latest02"
current_date = "20220516"
old_file = "rust_ppc64el_2022-05-06_03-05-rootfs.tar.zst"
old_sha256 = "dcfadadce8e68bbc33b9be5e1a50fce7e7a31b5528c1f7c1e1e9ace412039e55"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-05-16_03-06-rootfs.tar.zst
# SHA256SUM=c6c5ceeffe03ef165aaf86ea6a889e56e1288cf51d785cd638e258c7f8de1fd2
# BUILD_DATE=20220516
# BUILD_TAG=2022-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-16
begin = 2022-05-16 02:52:33.481126784+00:00
start-sync_0 = 02:59:05
start-zstd = 03:00:01
start-sync_1 = 03:05:58
end-sync_1 = 03:06:20
end = 2022-05-16 03:06:20.301693846+00:00

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
cargo = 'cargo 1.63.0-nightly (3f052d8ee 2022-05-12)'
rustc = 'rustc 1.63.0-nightly (42e1761c7 2022-05-15)'
cc = 'cc (Debian 11.3.0-1) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (3f052d8ee 2022-05-12)
release: 1.63.0-nightly
commit-hash: 3f052d8eed98c6a24f8b332fb2e6e6249d12d8c1
commit-date: 2022-05-12
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (42e1761c7 2022-05-15)
binary: rustc
commit-hash: 42e1761c704f074b7b8c7ff8a7433acfd65d2ee9
commit-date: 2022-05-15
host: powerpc64le-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.4
'''
```
