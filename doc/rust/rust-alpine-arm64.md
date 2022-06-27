# rust-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-arm64 \
    cake233/rust-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-arm64 bash
```
<!-- repo=cake233/rust-alpine-arm64 -->

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
    cake233/rust-alpine-arm64 \
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
    cake233/rust-alpine-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-arm64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2022-06-27", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-06-27_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f63193fda0777078a2ad2f2c2243f1da6caea0c1397411d6c28b616f3c42ab00"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "756M"
tar_bytes = 792689152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "145M"
zstd_bytes = 151351413

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220624"
previous_tag = "2022-06-24"
previous_file = "rust-musl_arm64_2022-06-24_03-00-rootfs.tar.zst"
previous_sha256 = "df0a683169ff471ebb8c2d71a176698468ea1aef67677d2364cb62d6ef40f8c1"

current_version = "latest02"
current_date = "20220627"
old_file = "rust-musl_arm64_2022-06-20_02-59-rootfs.tar.zst"
old_sha256 = "c35966a221e4b421a5f0af44f51bdfc0b316e83f2c12c61f77ff757384ddaef7"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-06-27_03-00-rootfs.tar.zst
# SHA256SUM=f63193fda0777078a2ad2f2c2243f1da6caea0c1397411d6c28b616f3c42ab00
# BUILD_DATE=20220627
# BUILD_TAG=2022-06-27
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-27
begin = 2022-06-27 02:52:27.234502215+00:00
start-sync_0 = 02:54:37
start-zstd = 02:55:17
start-sync_1 = 02:59:52
end-sync_1 = 03:00:06
end = 2022-06-27 03:00:06.864823769+00:00

[server]
repo = "cake233/rust-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.64.0-nightly (a5e08c470 2022-06-23)'
rustc = 'rustc 1.64.0-nightly (c80c4b8fd 2022-06-26)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.64.0-nightly (a5e08c470 2022-06-23)
release: 1.64.0-nightly
commit-hash: a5e08c4703f202e30cdaf80ca3e7c00baa59c496
commit-date: 2022-06-23
host: aarch64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (c80c4b8fd 2022-06-26)
binary: rustc
commit-hash: c80c4b8fdcf3da69cd483e2fec172c9b1f95842c
commit-date: 2022-06-26
host: aarch64-unknown-linux-musl
release: 1.64.0-nightly
LLVM version: 14.0.5
'''
```
