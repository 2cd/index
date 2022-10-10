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
tag = ["alpine", "2022-10-10", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_arm64_2022-10-10_03-02.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3c1007f2887fc7eacfd2c35ae42aa535499597b9aa616c1b751c2a2db7415ca5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "784M"
tar_bytes = 821449216

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "152M"
zstd_bytes = 158380642

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221007"
previous_tag = "2022-10-07"
previous_file = "rust-musl_arm64_2022-10-07_03-00-rootfs.tar.zst"
previous_sha256 = "870cffbe3242063d4626e662746ff6ea663a8ba650cc867a16588276f415bb6d"

current_version = "latest02"
current_date = "20221010"
old_file = "rust-musl_arm64_2022-10-03_02-59-rootfs.tar.zst"
old_sha256 = "8cfaccf68bdea15d3f2c47d47e679771ef248233247c22a8f10e514ba88c1376"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust-musl_arm64_2022-10-10_03-02-rootfs.tar.zst
# SHA256SUM=3c1007f2887fc7eacfd2c35ae42aa535499597b9aa616c1b751c2a2db7415ca5
# BUILD_DATE=20221010
# BUILD_TAG=2022-10-10
# STATUS=completed
# VERSION=latest02
# END_TIME=03:02

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-10
begin = 2022-10-10 02:52:30.726293465+00:00
start-sync_0 = 02:54:59
start-zstd = 02:55:50
start-sync_1 = 03:01:51
end-sync_1 = 03:02:29
end = 2022-10-10 03:02:29.272683887+00:00

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
cargo = 'cargo 1.66.0-nightly (3cdf1ab25 2022-10-07)'
rustc = 'rustc 1.66.0-nightly (81f391930 2022-10-09)'
cc = 'cc (Alpine 12.2.1_git20220924-r2) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.66.0-nightly (3cdf1ab25 2022-10-07)
release: 1.66.0-nightly
commit-hash: 3cdf1ab25dc4fe56f890e8c7330d53a23ad905d3
commit-date: 2022-10-07
host: aarch64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (81f391930 2022-10-09)
binary: rustc
commit-hash: 81f391930301afbc121b7c468138069daa354bf8
commit-date: 2022-10-09
host: aarch64-unknown-linux-musl
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
