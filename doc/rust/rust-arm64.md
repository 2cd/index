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
tag = ["latest", "2022-11-14", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-11-14_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a4c1f2c7d259de846864dfde2b1f1893383507a8ebe4b4ee7fb444e23908a021"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1820149248

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "242M"
zstd_bytes = 253738136

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221111"
previous_tag = "2022-11-11"
previous_file = "rust_arm64_2022-11-11_03-09-rootfs.tar.zst"
previous_sha256 = "045d1993b0d71d515a9d103a4513269207ba0ea20842e85b3112cf050062ec5a"

current_version = "latest02"
current_date = "20221114"
old_file = "rust_arm64_2022-11-07_03-10-rootfs.tar.zst"
old_sha256 = "1a1eabc22190af8557258e9302dec928118d394a7f1ad430ef32211a7e13d24d"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-11-14_03-06-rootfs.tar.zst
# SHA256SUM=a4c1f2c7d259de846864dfde2b1f1893383507a8ebe4b4ee7fb444e23908a021
# BUILD_DATE=20221114
# BUILD_TAG=2022-11-14
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-14
begin = 2022-11-14 02:52:22.224176345+00:00
start-sync_0 = 02:58:57
start-zstd = 02:59:58
start-sync_1 = 03:05:45
end-sync_1 = 03:06:04
end = 2022-11-14 03:06:04.502245196+00:00

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
ldd = 'ldd (Debian GLIBC 2.36-5) 2.36'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.67.0-nightly (a3dfea71c 2022-11-11)'
rustc = 'rustc 1.67.0-nightly (e631891f7 2022-11-13)'
cc = 'cc (Debian 12.2.0-9) 12.2.0'
cargo_verbose = '''
cargo 1.67.0-nightly (a3dfea71c 2022-11-11)
release: 1.67.0-nightly
commit-hash: a3dfea71ca0c888a88111086898aa833c291d497
commit-date: 2022-11-11
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.67.0-nightly (e631891f7 2022-11-13)
binary: rustc
commit-hash: e631891f7ad40eac3ef58ec3c2b57ecd81e40615
commit-date: 2022-11-13
host: aarch64-unknown-linux-gnu
release: 1.67.0-nightly
LLVM version: 15.0.4
'''
```
