# rust-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-amd64 bash
```
<!-- repo=cake233/rust-alpine-amd64 -->

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
    cake233/rust-alpine-amd64 \
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
    cake233/rust-alpine-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2023-03-03", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-03-03_12-32.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c668e41985652a12b6ecd223b9d580a9fad16d5fd1d902af0c8205dbdf6eeb30"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "804M"
tar_bytes = 842556928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "162M"
zstd_bytes = 169851300

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230227"
previous_tag = "2023-02-27"
previous_file = "rust-musl_amd64_2023-02-27_02-59-rootfs.tar.zst"
previous_sha256 = "9b38f7b71c33cb6448fe0cbc811b2eed87d22d441368331f2094e5e0ef71d2ec"

current_version = "latest02"
current_date = "20230303"
old_file = "rust-musl_amd64_2023-02-24_03-00-rootfs.tar.zst"
old_sha256 = "d513c753d4b6e59c971ff41820790f05a1889d715c997a4062e752e0dbb391b1"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-03-03_12-32-rootfs.tar.zst
# SHA256SUM=c668e41985652a12b6ecd223b9d580a9fad16d5fd1d902af0c8205dbdf6eeb30
# BUILD_DATE=20230303
# BUILD_TAG=2023-03-03
# STATUS=completed
# VERSION=latest02
# END_TIME=12:32

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-03
begin = 2023-03-03 12:24:50.341681924+00:00
start-sync_0 = 12:25:31
start-zstd = 12:26:19
start-sync_1 = 12:32:10
end-sync_1 = 12:32:29
end = 2023-03-03 12:32:29.315031297+00:00

[server]
repo = "cake233/rust-alpine-amd64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
rustup = 'rustup 1.25.2 (2023-02-01)'
cargo = 'cargo 1.69.0-nightly (9880b408a 2023-02-28)'
rustc = 'rustc 1.69.0-nightly (13471d3b2 2023-03-02)'
cc = 'cc (Alpine 12.2.1_git20220924-r9) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.69.0-nightly (9880b408a 2023-02-28)
release: 1.69.0-nightly
commit-hash: 9880b408a3af50c08fab3dbf4aa2a972df71e951
commit-date: 2023-02-28
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.18_alpha20230208 [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (13471d3b2 2023-03-02)
binary: rustc
commit-hash: 13471d3b2046cce78181dde6cfc146c09f55e29e
commit-date: 2023-03-02
host: x86_64-unknown-linux-musl
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
