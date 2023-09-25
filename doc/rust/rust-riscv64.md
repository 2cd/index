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
tag = ["latest", "2023-01-30", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2023-01-30_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "79660a9734705ec8a29f52a96fe98509dc9342c45cb520ab9d446b64cecee42c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1645508608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "208M"
zstd_bytes = 217512983

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230127"
previous_tag = "2023-01-27"
previous_file = "rust_riscv64_2023-01-27_03-09-rootfs.tar.zst"
previous_sha256 = "76c5511fc92cb66e1e3e9765def92db9cb81b3a605cdd323bb153fb8b9237a5a"

current_version = "latest01"
current_date = "20230130"
old_file = "rust_riscv64_2023-01-23_03-07-rootfs.tar.zst"
old_sha256 = "0678eaf2c603d3d4ff27bf79885e04a86c88a08af69b5012b51f884aee30c7eb"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2023-01-30_03-06-rootfs.tar.zst
# SHA256SUM=79660a9734705ec8a29f52a96fe98509dc9342c45cb520ab9d446b64cecee42c
# BUILD_DATE=20230130
# BUILD_TAG=2023-01-30
# STATUS=completed
# VERSION=latest01
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-01-30
begin = 2023-01-30 02:52:25.423941640+00:00
start-sync_0 = 03:00:40
start-zstd = 03:01:36
start-sync_1 = 03:06:28
end-sync_1 = 03:06:45
end = 2023-01-30 03:06:45.069569886+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-8) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.69.0-nightly (3c5af6bed 2023-01-24)'
rustc = 'rustc 1.69.0-nightly (e972bc808 2023-01-29)'
cc = 'cc (Debian 12.2.0-14) 12.2.0'
cargo_verbose = '''
cargo 1.69.0-nightly (3c5af6bed 2023-01-24)
release: 1.69.0-nightly
commit-hash: 3c5af6bed9a1a243a693e8e22ee2486bd5b82a6c
commit-date: 2023-01-24
host: riscv64gc-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.16.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.69.0-nightly (e972bc808 2023-01-29)
binary: rustc
commit-hash: e972bc8083d5228536dfd42913c8778b6bb04c8e
commit-date: 2023-01-29
host: riscv64gc-unknown-linux-gnu
release: 1.69.0-nightly
LLVM version: 15.0.7
'''
```