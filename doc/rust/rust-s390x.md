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
tag = ["latest", "2023-10-27", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-10-27_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f6f059933568120f86a3d1555a7c0fe634dccc0765db900ac55976d306f79755"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.9G"
tar_bytes = 2033718784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "243M"
zstd_bytes = 254068712

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231023"
previous_tag = "2023-10-23"
previous_file = "rust_s390x_2023-10-23_03-08-rootfs.tar.zst"
previous_sha256 = "a5cf91bb45e8a9f13ca74bd047ac9fd446433f2af9afecef9ce8f6515a6e27ed"

current_version = "latest01"
current_date = "20231027"
old_file = "rust_s390x_2023-10-20_03-09-rootfs.tar.zst"
old_sha256 = "e5b2723c483e9c3fd6dda0be470dbf1f88f0b68d7051b26f4d51ad5b193e4176"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-10-27_03-10-rootfs.tar.zst
# SHA256SUM=f6f059933568120f86a3d1555a7c0fe634dccc0765db900ac55976d306f79755
# BUILD_DATE=20231027
# BUILD_TAG=2023-10-27
# STATUS=completed
# VERSION=latest01
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-27
begin = 2023-10-27 02:52:42.233571886+00:00
start-sync_0 = 03:01:15
start-zstd = 03:02:46
start-sync_1 = 03:10:30
end-sync_1 = 03:10:56
end = 2023-10-27 03:10:56.523939370+00:00

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
cargo = 'cargo 1.75.0-nightly (df3509237 2023-10-24)'
rustc = 'rustc 1.75.0-nightly (aa1a71e9e 2023-10-26)'
cc = 'cc (Debian 13.2.0-6) 13.2.0'
cargo_verbose = '''
cargo 1.75.0-nightly (df3509237 2023-10-24)
release: 1.75.0-nightly
commit-hash: df3509237935f9418351b77803df7bc05c009b3d
commit-date: 2023-10-24
host: s390x-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.4.0-DEV (sys:0.4.68+curl-8.4.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.75.0-nightly (aa1a71e9e 2023-10-26)
binary: rustc
commit-hash: aa1a71e9e90f6eb3aed8cf79fc80bea304c17ecb
commit-date: 2023-10-26
host: s390x-unknown-linux-gnu
release: 1.75.0-nightly
LLVM version: 17.0.3
'''
```
