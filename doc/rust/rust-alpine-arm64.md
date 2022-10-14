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
tag = ["alpine", "2022-10-14", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-10-14_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "45201ae8427b3c6e1bfe8b28a0a2b0edd0c0c88572a4756241a04d6479bcd0c2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "785M"
tar_bytes = 822176256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "152M"
zstd_bytes = 158470304

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221010"
previous_tag = "2022-10-10"
previous_file = "rust-musl_arm64_2022-10-10_03-02-rootfs.tar.zst"
previous_sha256 = "3c1007f2887fc7eacfd2c35ae42aa535499597b9aa616c1b751c2a2db7415ca5"

current_version = "latest01"
current_date = "20221014"
old_file = "rust-musl_arm64_2022-10-07_03-00-rootfs.tar.zst"
old_sha256 = "870cffbe3242063d4626e662746ff6ea663a8ba650cc867a16588276f415bb6d"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-10-14_03-00-rootfs.tar.zst
# SHA256SUM=45201ae8427b3c6e1bfe8b28a0a2b0edd0c0c88572a4756241a04d6479bcd0c2
# BUILD_DATE=20221014
# BUILD_TAG=2022-10-14
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-14
begin = 2022-10-14 02:52:24.949602439+00:00
start-sync_0 = 02:54:32
start-zstd = 02:55:14
start-sync_1 = 02:59:59
end-sync_1 = 03:00:16
end = 2022-10-14 03:00:16.830076280+00:00

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
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (b8f30cb23 2022-10-10)'
rustc = 'rustc 1.66.0-nightly (6b3ede3f7 2022-10-13)'
cc = 'cc (Alpine 12.2.1_git20220924-r2) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.66.0-nightly (b8f30cb23 2022-10-10)
release: 1.66.0-nightly
commit-hash: b8f30cb23c4e5f20854a4f683325782b7cff9837
commit-date: 2022-10-10
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (6b3ede3f7 2022-10-13)
binary: rustc
commit-hash: 6b3ede3f7bc502eba7bbd202b4b9312d812adcd7
commit-date: 2022-10-13
host: aarch64-unknown-linux-musl
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
