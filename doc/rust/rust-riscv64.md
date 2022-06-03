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
tag = ["latest", "2022-06-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-06-03_03-04.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "088f94682fe5f46358141feed3fe21030a552da86925eb93b3d57a9744c5f3b5"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1693100032

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 232013138

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220530"
previous_tag = "2022-05-30"
previous_file = "rust_riscv64_2022-05-30_03-04-rootfs.tar.zst"
previous_sha256 = "42e312114298607b5f77b2cf1300a16ba0f35aacc98a335240b6e7d0fd81aaae"

current_version = "latest01"
current_date = "20220603"
old_file = "rust_riscv64_2022-05-27_03-06-rootfs.tar.zst"
old_sha256 = "73e82cfbd8b02d6e7ed0cf3d626f703ca41836ad39b0b7ea3dcc7ec792028501"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-06-03_03-04-rootfs.tar.zst
# SHA256SUM=088f94682fe5f46358141feed3fe21030a552da86925eb93b3d57a9744c5f3b5
# BUILD_DATE=20220603
# BUILD_TAG=2022-06-03
# STATUS=completed
# VERSION=latest01
# END_TIME=03:04

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-03
begin = 2022-06-03 02:52:31.931935159+00:00
start-sync_0 = 02:58:34
start-zstd = 02:59:29
start-sync_1 = 03:04:37
end-sync_1 = 03:04:55
end = 2022-06-03 03:04:55.821994497+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (38472bc19 2022-05-31)'
rustc = 'rustc 1.63.0-nightly (e71440575 2022-06-02)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (38472bc19 2022-05-31)
release: 1.63.0-nightly
commit-hash: 38472bc19f2f76e245eba54a6e97ee6821b3c1db
commit-date: 2022-05-31
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (e71440575 2022-06-02)
binary: rustc
commit-hash: e71440575c930dcecac288b7c3536410d688b351
commit-date: 2022-06-02
host: riscv64gc-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.4
'''
```
