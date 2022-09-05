# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-09-05", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-09-05_03-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "938d0e6a93aff91dde2f839e4bc7801b9fc0d409da4c6dd52c475c28ec18aeb5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1919866368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "272M"
zstd_bytes = 284288964

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220902"
previous_tag = "2022-09-02"
previous_file = "rust_arm64_2022-09-02_03-06-rootfs.tar.zst"
previous_sha256 = "7738662d304fb67c1ce6a852e97d9686a652a6db23c74170439b8eae5ad19453"

current_version = "latest02"
current_date = "20220905"
old_file = "rust_arm64_2022-08-29_03-07-rootfs.tar.zst"
old_sha256 = "318f0ccbc7423d273a15c46ddaca2e0095554c0224449651e5343bd03bf394b9"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-09-05_03-09-rootfs.tar.zst
# SHA256SUM=938d0e6a93aff91dde2f839e4bc7801b9fc0d409da4c6dd52c475c28ec18aeb5
# BUILD_DATE=20220905
# BUILD_TAG=2022-09-05
# STATUS=completed
# VERSION=latest02
# END_TIME=03:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-05
begin = 2022-09-05 02:52:26.615226793+00:00
start-sync_0 = 03:00:08
start-zstd = 03:01:25
start-sync_1 = 03:08:54
end-sync_1 = 03:09:22
end = 2022-09-05 03:09:22.075085158+00:00

[server]
repo = "cake233/rust-arm64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.34-7) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (4ed54cecc 2022-08-27)'
rustc = 'rustc 1.65.0-nightly (289279de1 2022-09-04)'
cc = 'cc (Debian 12.2.0-1) 12.2.0'
cargo_verbose = '''
cargo 1.65.0-nightly (4ed54cecc 2022-08-27)
release: 1.65.0-nightly
commit-hash: 4ed54cecce3ce9ab6ff058781f4c8a500ee6b8b5
commit-date: 2022-08-27
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (289279de1 2022-09-04)
binary: rustc
commit-hash: 289279de116707f28cf9c18e4bbb8c6ec84ad75b
commit-date: 2022-09-04
host: aarch64-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
