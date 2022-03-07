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
tag = ["alpine", "2022-03-07", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "rust-musl_amd64_2022-03-07_02-56.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "2dc1663a158e030f724dce157f3e22126158a08c905960296382f389cf20683a"

# zstd: [1-22]
zstd-level = 18

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "734M"
tar_bytes = 768846336

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "176M"
zstd_bytes = 183976726

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220304"
previous_tag = "2022-03-04"
previous_file = "rust-musl_amd64_2022-03-04_02-56-rootfs.tar.zst"
previous_sha256 = "8525df290e36fd0d88a950965ab77796f078f2242a57eda57d5259cb7a27045a"

current_version = "latest01"
current_date = "20220307"
old_file = "rust-musl_amd64_2022-02-28_02-57-rootfs.tar.zst"
old_sha256 = "f7d11686d95c8721d626f2bac8d893f803563ae31a3f8c7f3c463450e135288c"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-03-07_02-56-rootfs.tar.zst
# SHA256SUM=2dc1663a158e030f724dce157f3e22126158a08c905960296382f389cf20683a
# BUILD_DATE=20220307
# BUILD_TAG=2022-03-07
# STATUS=completed
# VERSION=latest01
# END_TIME=02:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-07
begin = 2022-03-07 02:52:32.022706057+00:00
start-sync_0 = 02:53:27
start-zstd = 02:54:08
start-sync_1 = 02:56:26
end-sync_1 = 02:56:43
end = 2022-03-07 02:56:43.355689072+00:00

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
cargo = 'cargo 1.61.0-nightly (3d6970d50 2022-02-28)'
rustc = 'rustc 1.61.0-nightly (38a0b81b1 2022-03-06)'
cc = 'cc (Alpine 11.2.1_git20220219) 11.2.1 20220219'
cargo_verbose = '''
cargo 1.61.0-nightly (3d6970d50 2022-02-28)
release: 1.61.0-nightly
commit-hash: 3d6970d50e30e797b8e26b2b9b1bdf92dc381f34
commit-date: 2022-02-28
host: x86_64-unknown-linux-musl
libgit2: 1.3.0 (sys:0.13.23 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Alpine Linux 3.15.0_alpha20210804 [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (38a0b81b1 2022-03-06)
binary: rustc
commit-hash: 38a0b81b1c32764d6a583a5efb6f306b8c44c503
commit-date: 2022-03-06
host: x86_64-unknown-linux-musl
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
