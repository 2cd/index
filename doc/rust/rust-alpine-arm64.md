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
tag = ["alpine", "2023-03-27", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-03-27_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "fdc336da880e6ddcd278e6f6318c192779b0591ee02849202a4762285769c4ae"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "858M"
tar_bytes = 899210752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "157M"
zstd_bytes = 163754004

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230324"
previous_tag = "2023-03-24"
previous_file = "rust-musl_arm64_2023-03-24_03-00-rootfs.tar.zst"
previous_sha256 = "0a04ff6372e97244c4983be515738042ed733441bbc744681672abd3f2c1a2cb"

current_version = "latest01"
current_date = "20230327"
old_file = "rust-musl_arm64_2023-03-20_03-00-rootfs.tar.zst"
old_sha256 = "1a88204dcdc7b89cd74a9a8d14f3ed35c6ec9f65cf509878e4940dc8cfefb5d7"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-03-27_03-01-rootfs.tar.zst
# SHA256SUM=fdc336da880e6ddcd278e6f6318c192779b0591ee02849202a4762285769c4ae
# BUILD_DATE=20230327
# BUILD_TAG=2023-03-27
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-27
begin = 2023-03-27 02:52:34.261543676+00:00
start-sync_0 = 02:54:51
start-zstd = 02:55:41
start-sync_1 = 03:01:13
end-sync_1 = 03:01:32
end = 2023-03-27 03:01:33.019436212+00:00

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
rustup = 'rustup 1.25.2 (17db695f1 2023-02-01)'
cargo = 'cargo 1.70.0-nightly (15d090969 2023-03-21)'
rustc = 'rustc 1.70.0-nightly (db0cbc48d 2023-03-26)'
cc = 'cc (Alpine 12.2.1_git20220924-r9) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.70.0-nightly (15d090969 2023-03-21)
release: 1.70.0-nightly
commit-hash: 15d090969743630bff549a1b068bcaa8174e5ee3
commit-date: 2023-03-21
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 8.0.1-DEV (sys:0.4.61+curl-8.0.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.18_alpha20230208 [64-bit]
'''
rustc_verbose = '''
rustc 1.70.0-nightly (db0cbc48d 2023-03-26)
binary: rustc
commit-hash: db0cbc48d4aaa300713a95d9b317a365a474490c
commit-date: 2023-03-26
host: aarch64-unknown-linux-musl
release: 1.70.0-nightly
LLVM version: 16.0.0
'''
```
