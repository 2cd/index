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
tag = ["latest", "2022-11-21", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-11-21_03-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5c69b49efbb764eb5b81f8ccf93da6a29e7de99e08533c0f7862c689a8e1301e"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1644437504

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "208M"
zstd_bytes = 217887683

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221118"
previous_tag = "2022-11-18"
previous_file = "rust_riscv64_2022-11-18_03-09-rootfs.tar.zst"
previous_sha256 = "0d4c5ed7e9abab8813275d660ed50e6b81d1ca7e84443c5911e2cf55a00c6663"

current_version = "latest01"
current_date = "20221121"
old_file = "rust_riscv64_2022-11-14_03-07-rootfs.tar.zst"
old_sha256 = "9ef8085cfe50f3e1f661a1ac76e1bc3f471cb2c5108b8a2f2b14b4b18079e652"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-11-21_03-08-rootfs.tar.zst
# SHA256SUM=5c69b49efbb764eb5b81f8ccf93da6a29e7de99e08533c0f7862c689a8e1301e
# BUILD_DATE=20221121
# BUILD_TAG=2022-11-21
# STATUS=completed
# VERSION=latest01
# END_TIME=03:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-21
begin = 2022-11-21 02:52:27.057550563+00:00
start-sync_0 = 03:00:51
start-zstd = 03:01:58
start-sync_1 = 03:07:45
end-sync_1 = 03:08:11
end = 2022-11-21 03:08:11.729908143+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (eb5d35917 2022-11-17)'
rustc = 'rustc 1.67.0-nightly (a28f3c88e 2022-11-20)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (eb5d35917 2022-11-17)
release: 1.67.0-nightly
commit-hash: eb5d35917b2395194593c9ca70c3778f60c1573b
commit-date: 2022-11-17
host: riscv64gc-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (a28f3c88e 2022-11-20)
binary: rustc
commit-hash: a28f3c88e50a77bc2a91889241248c4543854e61
commit-date: 2022-11-20
host: riscv64gc-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
