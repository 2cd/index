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
tag = ["alpine", "2022-11-04", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-11-04_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "50c278d74a4062752646d5ed4e2bc143d4f35f72a77cc87f81ea17a80a874f67"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "808M"
tar_bytes = 846710272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170348809

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221031"
previous_tag = "2022-10-31"
previous_file = "rust-musl_amd64_2022-10-31_03-00-rootfs.tar.zst"
previous_sha256 = "eda568cb1f380a5c765b51479aab2ceb548706da73ddde4059ced706f6f7148c"

current_version = "latest02"
current_date = "20221104"
old_file = "rust-musl_amd64_2022-10-28_03-00-rootfs.tar.zst"
old_sha256 = "e264b62a0653984b0059a2823da2238f68b96841e021361e288d72e3df20c4db"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-11-04_03-00-rootfs.tar.zst
# SHA256SUM=50c278d74a4062752646d5ed4e2bc143d4f35f72a77cc87f81ea17a80a874f67
# BUILD_DATE=20221104
# BUILD_TAG=2022-11-04
# STATUS=completed
# VERSION=latest02
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-04
begin = 2022-11-04 02:52:23.362848842+00:00
start-sync_0 = 02:53:21
start-zstd = 02:54:09
start-sync_1 = 02:59:59
end-sync_1 = 03:00:18
end = 2022-11-04 03:00:18.152654252+00:00

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
rustup = 'rustup 1.25.1 (2022-07-12)'
cargo = 'cargo 1.67.0-nightly (7e484fc1a 2022-10-27)'
rustc = 'rustc 1.67.0-nightly (edf018221 2022-11-02)'
cc = 'cc (Alpine 12.2.1_git20220924-r4) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.67.0-nightly (7e484fc1a 2022-10-27)
release: 1.67.0-nightly
commit-hash: 7e484fc1a766f56dbc95380f45719698e0c82749
commit-date: 2022-10-27
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (edf018221 2022-11-02)
binary: rustc
commit-hash: edf0182213a9e30982eb34f3925ddc4cf5ed3471
commit-date: 2022-11-02
host: x86_64-unknown-linux-musl
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
