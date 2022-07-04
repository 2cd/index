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
tag = ["alpine", "2022-07-04", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-07-04_02-59.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "783f787c154fb440ca4b705c227b631b9161dafccf5924b244ac02a0c9f7875c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "761M"
tar_bytes = 796982272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "148M"
zstd_bytes = 154608472

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220701"
previous_tag = "2022-07-01"
previous_file = "rust-musl_arm64_2022-07-01_03-00-rootfs.tar.zst"
previous_sha256 = "04ada3c24f4e23625094dc6391af9436c1ad11b4e5c6e466fe71c3b18c88f179"

current_version = "latest02"
current_date = "20220704"
old_file = "rust-musl_arm64_2022-06-27_03-00-rootfs.tar.zst"
old_sha256 = "f63193fda0777078a2ad2f2c2243f1da6caea0c1397411d6c28b616f3c42ab00"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-07-04_02-59-rootfs.tar.zst
# SHA256SUM=783f787c154fb440ca4b705c227b631b9161dafccf5924b244ac02a0c9f7875c
# BUILD_DATE=20220704
# BUILD_TAG=2022-07-04
# STATUS=completed
# VERSION=latest02
# END_TIME=02:59

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-04
begin = 2022-07-04 02:52:28.629402426+00:00
start-sync_0 = 02:54:21
start-zstd = 02:54:59
start-sync_1 = 02:59:20
end-sync_1 = 02:59:33
end = 2022-07-04 02:59:33.337600271+00:00

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
cargo = 'cargo 1.64.0-nightly (dbff32b27 2022-06-24)'
rustc = 'rustc 1.64.0-nightly (495b21669 2022-07-03)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.64.0-nightly (dbff32b27 2022-06-24)
release: 1.64.0-nightly
commit-hash: dbff32b27893b899ae2397f3d56d1be111041d56
commit-date: 2022-06-24
host: aarch64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (495b21669 2022-07-03)
binary: rustc
commit-hash: 495b216696ccbc27c73d6bdc486bf4621d610f4b
commit-date: 2022-07-03
host: aarch64-unknown-linux-musl
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
