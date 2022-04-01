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
tag = ["alpine", "2022-04-01", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-musl_amd64_2022-04-01_02-01.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "3e47dd6b9a867115f117797bf6e92ca8efa9bcbb439a97f1bf019046fc2c9c80"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "746M"
tar_bytes = 781427200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 160476037

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220328"
previous_tag = "2022-03-28"
previous_file = "rust-musl_amd64_2022-03-28_02-01-rootfs.tar.zst"
previous_sha256 = "152e15155495554f29dc32b3bd3170d744ca719c6c1d278ed9e7d6922aae4d61"

current_version = "latest01"
current_date = "20220401"
old_file = "rust-musl_amd64_2022-03-25_02-59-rootfs.tar.zst"
old_sha256 = "e0aef1cdee02829912a825add74eb87df08d5c4b0f77c1deab07b651e02bb59a"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-04-01_02-01-rootfs.tar.zst
# SHA256SUM=3e47dd6b9a867115f117797bf6e92ca8efa9bcbb439a97f1bf019046fc2c9c80
# BUILD_DATE=20220401
# BUILD_TAG=2022-04-01
# STATUS=completed
# VERSION=latest01
# END_TIME=02:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-01
begin = 2022-04-01 01:52:29.868789497+00:00
start-sync_0 = 01:53:25
start-zstd = 01:54:19
start-sync_1 = 02:00:45
end-sync_1 = 02:01:04
end = 2022-04-01 02:01:04.921741403+00:00

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
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
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
ldd = 'musl libc (x86_64) Version 1.2.2'
rustup = 'rustup 1.24.3 (2021-05-31)'
cargo = 'cargo 1.61.0-nightly (1ef1e0a12 2022-03-31)'
rustc = 'rustc 1.61.0-nightly (0677edc86 2022-03-31)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.61.0-nightly (1ef1e0a12 2022-03-31)
release: 1.61.0-nightly
commit-hash: 1ef1e0a12723ce9548d7da2b63119de9002bead8
commit-date: 2022-03-31
host: x86_64-unknown-linux-musl
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.16.0_alpha20220328 [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (0677edc86 2022-03-31)
binary: rustc
commit-hash: 0677edc86e342f333d4828b0ee1ef395a4e70fe5
commit-date: 2022-03-31
host: x86_64-unknown-linux-musl
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
