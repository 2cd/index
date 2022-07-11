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
tag = ["latest", "2022-07-11", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "riscv64"
platform = "linux/riscv64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_riscv64_2022-07-11_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "187d6c011779c00dfdc6fbc69381bf3a2cf84a1c999aaf2e599b34a905d18717"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1697880576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "225M"
zstd_bytes = 235505904

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220708"
previous_tag = "2022-07-08"
previous_file = "rust_riscv64_2022-07-08_03-07-rootfs.tar.zst"
previous_sha256 = "872fc151d20e38046c4599eecb576db8d673c815923bcd3177b58b8273a42cd6"

current_version = "latest02"
current_date = "20220711"
old_file = "rust_riscv64_2022-07-04_03-08-rootfs.tar.zst"
old_sha256 = "9e6a36826755a69ab8111749c8c46a6af78bbec48c8835f74da32c643d50b0f9"
# edition 2021
# DISTRO_NAME=rust_riscv64
# ROOTFS_FILE=rust_riscv64_2022-07-11_03-05-rootfs.tar.zst
# SHA256SUM=187d6c011779c00dfdc6fbc69381bf3a2cf84a1c999aaf2e599b34a905d18717
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 02:52:27.670469437+00:00
start-sync_0 = 02:59:03
start-zstd = 03:00:02
start-sync_1 = 03:05:27
end-sync_1 = 03:05:55
end = 2022-07-11 03:05:55.749729148+00:00

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
cargo = 'cargo 1.64.0-nightly (b1dd22e66 2022-07-09)'
rustc = 'rustc 1.64.0-nightly (c396bb3b8 2022-07-10)'
cc = 'cc (Debian 11.3.0-4) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (b1dd22e66 2022-07-09)
release: 1.64.0-nightly
commit-hash: b1dd22e668af5279e13a071ad4b17435bd6bfa4c
commit-date: 2022-07-09
host: riscv64gc-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (c396bb3b8 2022-07-10)
binary: rustc
commit-hash: c396bb3b8a16b1f2762b7c6078dc3e023f6a2493
commit-date: 2022-07-10
host: riscv64gc-unknown-linux-gnu
release: 1.64.0-nightly
LLVM version: 14.0.6
'''
```
