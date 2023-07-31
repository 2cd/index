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
tag = ["alpine", "2023-07-31", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2023-07-31_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "15153c58ceba3d64ec9f10002140945d3b44966061623db69001bd16395f8b94"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "866M"
tar_bytes = 907868672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "154M"
zstd_bytes = 161211308

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230728"
previous_tag = "2023-07-28"
previous_file = "rust-musl_arm64_2023-07-28_03-01-rootfs.tar.zst"
previous_sha256 = "ef54ba9839904ba4395448431770741a13535b6a2089905c944bbf4a3f73f770"

current_version = "latest01"
current_date = "20230731"
old_file = "rust-musl_arm64_2023-07-24_03-00-rootfs.tar.zst"
old_sha256 = "2586db489c4abb395b576a16e5c761d32ada6a445182d592b96545dd834268d4"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2023-07-31_03-01-rootfs.tar.zst
# SHA256SUM=15153c58ceba3d64ec9f10002140945d3b44966061623db69001bd16395f8b94
# BUILD_DATE=20230731
# BUILD_TAG=2023-07-31
# STATUS=completed
# VERSION=latest01
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-31
begin = 2023-07-31 02:52:37.415657603+00:00
start-sync_0 = 02:54:57
start-zstd = 02:55:45
start-sync_1 = 03:01:34
end-sync_1 = 03:01:54
end = 2023-07-31 03:01:54.037789336+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.73.0-nightly (7ac9416d8 2023-07-24)'
rustc = 'rustc 1.73.0-nightly (32303b219 2023-07-29)'
cc = 'cc (Alpine 13.1.1_git20230722) 13.1.1 20230722'
cargo_verbose = '''
cargo 1.73.0-nightly (7ac9416d8 2023-07-24)
release: 1.73.0-nightly
commit-hash: 7ac9416d82cd4fc5e707c9ec3574d22dff6466e5
commit-date: 2023-07-24
host: aarch64-unknown-linux-musl
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Alpine Linux 3.18_alpha20230329 [64-bit]
'''
rustc_verbose = '''
rustc 1.73.0-nightly (32303b219 2023-07-29)
binary: rustc
commit-hash: 32303b219d4dffa447aa606bc11c7a648f44a862
commit-date: 2023-07-29
host: aarch64-unknown-linux-musl
release: 1.73.0-nightly
LLVM version: 16.0.5
'''
```
