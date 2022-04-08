# rust-riscv64

## How to run it?

```sh
docker run \
    -it \
    --name rust-riscv64 \
    cake233/rust-riscv64
```

## How to exec shell?

```sh
docker exec -it rust-riscv64 bash
```
<!-- repo=cake233/rust-riscv64 -->

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
    cake233/rust-riscv64 \
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
    cake233/rust-riscv64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-riscv64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-04-08", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
x11_or_wayland = false

[file]
name = "rust_riscv64_2022-04-08_02-04.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f7bc4ee72742fe25a955d8ad4a45ddec82ea602d901e3fbdb42cc034494a5d78"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1673564672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 232748279

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220404"
previous_tag = "2022-04-04"
previous_file = "rust_riscv64_2022-04-04_02-04-rootfs.tar.zst"
previous_sha256 = "8601ecd8e78d609eb5c3b4a4727d4430088e08888674eb11180b04423b3b4c15"

current_version = "latest02"
current_date = "20220408"
old_file = "rust_riscv64_2022-04-01_02-06-rootfs.tar.zst"
old_sha256 = "961c3b3b7b28ace5b4c0106886adcd736de94e6a98a4092507c2e1e06776dbf5"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-04-08_02-04-rootfs.tar.zst
# SHA256SUM=f7bc4ee72742fe25a955d8ad4a45ddec82ea602d901e3fbdb42cc034494a5d78
# BUILD_DATE=20220408
# BUILD_TAG=2022-04-08
# STATUS=completed
# VERSION=latest02
# END_TIME=02:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-08
begin = 2022-04-08 01:52:30.186622643+00:00
start-sync_0 = 01:58:21
start-zstd = 01:59:22
start-sync_1 = 02:04:26
end-sync_1 = 02:04:49
end = 2022-04-08 02:04:49.919358233+00:00

[server]
repo = "cake233/rust-riscv64"

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
LANG = "en_US.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.62.0-nightly (e2e2dddeb 2022-04-05)'
rustc = 'rustc 1.62.0-nightly (e745b4ddb 2022-04-07)'
cc = 'cc (Debian 11.2.0-19) 11.2.0'
cargo_verbose = '''
cargo 1.62.0-nightly (e2e2dddeb 2022-04-05)
release: 1.62.0-nightly
commit-hash: e2e2dddebe66dfc1403a312653557e332445308b
commit-date: 2022-04-05
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (e745b4ddb 2022-04-07)
binary: rustc
commit-hash: e745b4ddbd05026c75aae4506aef39fdfe1603c5
commit-date: 2022-04-07
host: riscv64gc-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.0
'''
```
