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
tag = ["latest", "2022-08-19", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-08-19_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ffd1784098259a6c51555ec86f2ab5eb5e9c54a2d6728bcdf69c71248b81d6b0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1645776896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "232M"
zstd_bytes = 242801330

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220815"
previous_tag = "2022-08-15"
previous_file = "rust_riscv64_2022-08-15_03-05-rootfs.tar.zst"
previous_sha256 = "d1b99aeb0ab1d8a6169dd7df8fb974d0117dc8e2afd3ca2b2c153fc2eeb26a7b"

current_version = "latest01"
current_date = "20220819"
old_file = "rust_riscv64_2022-08-12_03-05-rootfs.tar.zst"
old_sha256 = "e45a1f93baa02f95679ffe0b45c5cb81890514e68585ad4c002c8ad2652194b5"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-08-19_03-05-rootfs.tar.zst
# SHA256SUM=ffd1784098259a6c51555ec86f2ab5eb5e9c54a2d6728bcdf69c71248b81d6b0
# BUILD_DATE=20220819
# BUILD_TAG=2022-08-19
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-19
begin = 2022-08-19 02:52:26.228887312+00:00
start-sync_0 = 02:59:43
start-zstd = 03:00:39
start-sync_1 = 03:05:37
end-sync_1 = 03:05:58
end = 2022-08-19 03:05:58.912824584+00:00

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
ldd = 'ldd (Debian GLIBC 2.34-4) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.65.0-nightly (9809f8ff3 2022-08-16)'
rustc = 'rustc 1.65.0-nightly (0b79f758c 2022-08-18)'
cc = 'cc (Debian 12.1.0-8) 12.1.0'
cargo_verbose = '''
cargo 1.65.0-nightly (9809f8ff3 2022-08-16)
release: 1.65.0-nightly
commit-hash: 9809f8ff33c2b998919fd0432c626f0f7323697a
commit-date: 2022-08-16
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.65.0-nightly (0b79f758c 2022-08-18)
binary: rustc
commit-hash: 0b79f758c9aa6646606662a6d623a0752286cd17
commit-date: 2022-08-18
host: riscv64gc-unknown-linux-gnu
release: 1.65.0-nightly
LLVM version: 15.0.0
'''
```
