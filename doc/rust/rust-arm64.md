# rust-arm64

## How to run it?

```sh
docker run \
    -it \
    --name rust-arm64 \
    cake233/rust-arm64
```

## How to exec shell?

```sh
docker exec -it rust-arm64 bash
```
<!-- repo=cake233/rust-arm64 -->

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
    cake233/rust-arm64 \
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
    cake233/rust-arm64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-arm64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2024-02-19", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2024-02-19_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8d410f3874a922ac510b9fc972c2a03dd731cedad8afd0b0786de349e4153294"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1912664576

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "250M"
zstd_bytes = 261285581

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "rust_arm64_2023-11-27_03-07-rootfs.tar.zst"
previous_sha256 = "d1760a87522557e3875f2da1e18fb3cbe4addb190015ebf98df6f933a1c936ed"

current_version = "latest01"
current_date = "20240219"
old_file = "rust_arm64_2023-11-24_03-06-rootfs.tar.zst"
old_sha256 = "33ca8752d76df601e6b82ba72fbb8681ffc9f4a3f46e5fab7c76f9e155a0972c"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2024-02-19_03-07-rootfs.tar.zst
# SHA256SUM=8d410f3874a922ac510b9fc972c2a03dd731cedad8afd0b0786de349e4153294
# BUILD_DATE=20240219
# BUILD_TAG=2024-02-19
# STATUS=completed
# VERSION=latest01
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-02-19
begin = 2024-02-19 02:52:35.793893205+00:00
start-sync_0 = 03:01:41
start-zstd = 03:02:31
start-sync_1 = 03:07:19
end-sync_1 = 03:07:34
end = 2024-02-19 03:07:34.887694677+00:00

[server]
repo = "cake233/rust-arm64"

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
ldd = 'ldd (Debian GLIBC 2.37-15) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.78.0-nightly (7b7af3077 2024-02-17)'
rustc = 'rustc 1.78.0-nightly (2bf78d12d 2024-02-18)'
cc = 'cc (Debian 13.2.0-13) 13.2.0'
cargo_verbose = '''
cargo 1.78.0-nightly (7b7af3077 2024-02-17)
release: 1.78.0-nightly
commit-hash: 7b7af3077bff8d60b7f124189bc9de227d3063a9
commit-date: 2024-02-17
host: aarch64-unknown-linux-gnu
libgit2: 1.7.2 (sys:0.18.2 vendored)
libcurl: 8.6.0-DEV (sys:0.4.71+curl-8.6.0 vendored ssl:OpenSSL/3.2.1)
ssl: OpenSSL 3.2.1 30 Jan 2024
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.78.0-nightly (2bf78d12d 2024-02-18)
binary: rustc
commit-hash: 2bf78d12d33ae02d10010309a0d85dd04e7cff72
commit-date: 2024-02-18
host: aarch64-unknown-linux-gnu
release: 1.78.0-nightly
LLVM version: 18.1.0
'''
```
