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
tag = ["latest", "2022-03-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
x11_or_wayland = false

[file]
name = "rust_riscv64_2022-03-11_03-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "af5aedf35a365cdccc998a252ba523bfcbb0bca0ff1b28c10013a34b400b7929"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.5G"
tar_bytes = 1609422848

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "218M"
zstd_bytes = 228003890

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "rust_riscv64_2022-03-07_03-06-rootfs.tar.zst"
previous_sha256 = "164878b16798b83320302b78ab0b3a7982a3220e9dc35dbf4f42636987f03a2a"

current_version = "latest02"
current_date = "20220311"
old_file = "rust_riscv64_2022-03-04_03-04-rootfs.tar.zst"
old_sha256 = "764a14d9d6baad69285bb2b0b7335d2edd767fe34c4d293565ac782321532034"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-03-11_03-07-rootfs.tar.zst
# SHA256SUM=af5aedf35a365cdccc998a252ba523bfcbb0bca0ff1b28c10013a34b400b7929
# BUILD_DATE=20220311
# BUILD_TAG=2022-03-11
# STATUS=completed
# VERSION=latest02
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-11
begin = 2022-03-11 02:52:30.272579051+00:00
start-sync_0 = 03:00:06
start-zstd = 03:01:15
start-sync_1 = 03:07:15
end-sync_1 = 03:07:38
end = 2022-03-11 03:07:38.164229114+00:00

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
cargo = 'cargo 1.61.0-nightly (65c826642 2022-03-09)'
rustc = 'rustc 1.61.0-nightly (5f4e06771 2022-03-10)'
cc = 'cc (Debian 11.2.0-18) 11.2.0'
cargo_verbose = '''
cargo 1.61.0-nightly (65c826642 2022-03-09)
release: 1.61.0-nightly
commit-hash: 65c82664263feddc5fe2d424be0993c28d46377a
commit-date: 2022-03-09
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.1 (sys:0.14.1 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1m)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.61.0-nightly (5f4e06771 2022-03-10)
binary: rustc
commit-hash: 5f4e0677190b82e61dc507e3e72caf89da8e5e28
commit-date: 2022-03-10
host: riscv64gc-unknown-linux-gnu
release: 1.61.0-nightly
LLVM version: 14.0.0
'''
```
