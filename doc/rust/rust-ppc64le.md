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
tag = ["latest", "2024-03-01", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2024-03-01_03-03.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "265ebc8e0bf0b83c9305f7606a0f9c9c44926d682f54b5f94b7e4fe7edb5ddb2"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1732012544

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "224M"
zstd_bytes = 234583365

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_ppc64el_2023-11-27_03-02-rootfs.tar.zst"
previous_sha256 = "b1ada3fb2e8f52a1963baf5be5bff055e54e7ab0805baa0a309c6b77a9998b55"

current_version = "latest02"
current_date = "20240301"
old_file = "rust_ppc64el_2023-11-24_03-02-rootfs.tar.zst"
old_sha256 = "a81223bcdb5870598ca1c4a4db2222404549b763a08f7760e1ccfc21edd1917b"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2024-03-01_03-03-rootfs.tar.zst
# SHA256SUM=265ebc8e0bf0b83c9305f7606a0f9c9c44926d682f54b5f94b7e4fe7edb5ddb2
# BUILD_DATE=20240301
# BUILD_TAG=2024-03-01
# STATUS=completed
# VERSION=latest02
# END_TIME=03:03

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-03-01
begin = 2024-03-01 02:52:37.672425958+00:00
start-sync_0 = 02:57:43
start-zstd = 02:58:31
start-sync_1 = 03:02:52
end-sync_1 = 03:03:05
end = 2024-03-01 03:03:05.985722851+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-15.1) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.78.0-nightly (8964c8ccf 2024-02-27)'
rustc = 'rustc 1.78.0-nightly (878c8a2a6 2024-02-29)'
cc = 'cc (Debian 13.2.0-16.1) 13.2.0'
cargo_verbose = '''
cargo 1.78.0-nightly (8964c8ccf 2024-02-27)
release: 1.78.0-nightly
commit-hash: 8964c8ccff6e420e2a38b8696d178d69fab84d9d
commit-date: 2024-02-27
host: powerpc64le-unknown-linux-gnu
libgit2: 1.7.2 (sys:0.18.2 vendored)
libcurl: 8.6.0-DEV (sys:0.4.71+curl-8.6.0 vendored ssl:OpenSSL/3.2.1)
ssl: OpenSSL 3.2.1 30 Jan 2024
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.78.0-nightly (878c8a2a6 2024-02-29)
binary: rustc
commit-hash: 878c8a2a62d49ca5c454547ad67290a1df746cb5
commit-date: 2024-02-29
host: powerpc64le-unknown-linux-gnu
release: 1.78.0-nightly
LLVM version: 18.1.0
'''
```
