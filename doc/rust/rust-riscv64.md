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
tag = ["latest", "2022-12-09", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-12-09_10-58.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a574b869504deb7e10d3a9247c52fa80cc0ce713485d1eb92007bcffbe980291"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1658322944

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "209M"
zstd_bytes = 218731335

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221205"
previous_tag = "2022-12-05"
previous_file = "rust_riscv64_2022-12-05_03-05-rootfs.tar.zst"
previous_sha256 = "d7cd0338a9a7f1d6ad711ecbe72aa35f4bfed85c34256b6cdb8502b4eaab54e3"

current_version = "latest01"
current_date = "20221209"
old_file = "rust_riscv64_2022-12-02_03-07-rootfs.tar.zst"
old_sha256 = "af0b56c369ae38fb00205bba216b8724bb3c0e3936a7aa0fe2c82753adf4fa05"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-12-09_10-58-rootfs.tar.zst
# SHA256SUM=a574b869504deb7e10d3a9247c52fa80cc0ce713485d1eb92007bcffbe980291
# BUILD_DATE=20221209
# BUILD_TAG=2022-12-09
# STATUS=completed
# VERSION=latest01
# END_TIME=10:58

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-09
begin = 2022-12-09 10:46:07.313916254+00:00
start-sync_0 = 10:52:19
start-zstd = 10:53:18
start-sync_1 = 10:57:57
end-sync_1 = 10:58:15
end = 2022-12-09 10:58:15.580860025+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-6) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (f6e737b1e 2022-12-02)'
rustc = 'rustc 1.67.0-nightly (7632db0e8 2022-12-08)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (f6e737b1e 2022-12-02)
release: 1.67.0-nightly
commit-hash: f6e737b1e3386adb89333bf06a01f68a91ac5306
commit-date: 2022-12-02
host: riscv64gc-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (7632db0e8 2022-12-08)
binary: rustc
commit-hash: 7632db0e87d8adccc9a83a47795c9411b1455855
commit-date: 2022-12-08
host: riscv64gc-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.6
'''
```
