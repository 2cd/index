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
tag = ["alpine", "2023-02-27", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2023-02-27_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "9b38f7b71c33cb6448fe0cbc811b2eed87d22d441368331f2094e5e0ef71d2ec"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "805M"
tar_bytes = 843243008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170206501

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230224"
previous_tag = "2023-02-24"
previous_file = "rust-musl_amd64_2023-02-24_03-00-rootfs.tar.zst"
previous_sha256 = "d513c753d4b6e59c971ff41820790f05a1889d715c997a4062e752e0dbb391b1"

current_version = "latest01"
current_date = "20230227"
old_file = "rust-musl_amd64_2023-02-20_02-59-rootfs.tar.zst"
old_sha256 = "605a740ae46092a848bff69698bd3f5ec861757661376d6df03a06723bf65daa"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2023-02-27_02-59-rootfs.tar.zst
# SHA256SUM=9b38f7b71c33cb6448fe0cbc811b2eed87d22d441368331f2094e5e0ef71d2ec
# BUILD_DATE=20230227
# BUILD_TAG=2023-02-27
# STATUS=completed
# VERSION=latest01
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-27
begin = 2023-02-27 02:52:31.328258920+00:00
start-sync_0 = 02:53:14
start-zstd = 02:53:55
start-sync_1 = 02:59:29
end-sync_1 = 02:59:43
end = 2023-02-27 02:59:43.810340587+00:00

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
cargo = 'cargo 1.69.0-nightly (9d5b32f50 2023-02-22)'
rustc = 'rustc 1.69.0-nightly (d962ea578 2023-02-26)'
cc = 'cc (Alpine 12.2.1_git20220924-r9) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.69.0-nightly (9d5b32f50 2023-02-22)
release: 1.69.0-nightly
commit-hash: 9d5b32f503fc099c4064298465add14d4bce11e6
commit-date: 2023-02-22
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.18_alpha20230208 [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (d962ea578 2023-02-26)
binary: rustc
commit-hash: d962ea57899d64dc8a57040142c6b498a57c8064
commit-date: 2023-02-26
host: x86_64-unknown-linux-musl
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```
