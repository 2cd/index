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
tag = ["latest", "2022-07-25", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-07-25_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3a88c584e91ab442bce8779b196ab68a8290f1349f9fa75f5600c4addf12324f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1718534144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238669602

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220718"
previous_tag = "2022-07-18"
previous_file = "rust_riscv64_2022-07-18_03-05-rootfs.tar.zst"
previous_sha256 = "fa4633c476191045034bb14f252e552441ecb4d2558009893db749c3da9c9814"

current_version = "latest01"
current_date = "20220725"
old_file = "rust_riscv64_2022-07-15_03-05-rootfs.tar.zst"
old_sha256 = "c279944c63b02260d5a390be7a494aae599c0894598aac7ef18cc0e2471c4862"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-07-25_03-06-rootfs.tar.zst
# SHA256SUM=3a88c584e91ab442bce8779b196ab68a8290f1349f9fa75f5600c4addf12324f
# BUILD_DATE=20220725
# BUILD_TAG=2022-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-25
begin = 2022-07-25 02:52:28.251926519+00:00
start-sync_0 = 02:59:15
start-zstd = 03:00:18
start-sync_1 = 03:06:19
end-sync_1 = 03:06:38
end = 2022-07-25 03:06:38.156642001+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.64.0-nightly (d8d30a753 2022-07-19)'
rustc = 'rustc 1.64.0-nightly (7fe022f5a 2022-07-24)'
cc = 'cc (Debian 12.1.0-5) 12.1.0'
cargo_verbose = '''
cargo 1.64.0-nightly (d8d30a753 2022-07-19)
release: 1.64.0-nightly
commit-hash: d8d30a75376f78bb0fabe3d28ee9d87aa8035309
commit-date: 2022-07-19
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (7fe022f5a 2022-07-24)
binary: rustc
commit-hash: 7fe022f5aa32bbbb33c3a58755729d6667a461a9
commit-date: 2022-07-24
host: riscv64gc-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
