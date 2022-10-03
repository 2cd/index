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
tag = ["latest", "2022-10-03", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_arm64_2022-10-03_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "109a96c2f9ddf43bb3d57827a167d2e51376e68dbb8a231b2072fbeb33a69c5f"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1926630400

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "271M"
zstd_bytes = 283429654

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220930"
previous_tag = "2022-09-30"
previous_file = "rust_arm64_2022-09-30_03-10-rootfs.tar.zst"
previous_sha256 = "789f29456d29ae59d145bba89e182618cdf99ba79cff77d8ffef8e14f51906c0"

current_version = "latest02"
current_date = "20221003"
old_file = "rust_arm64_2022-09-26_03-11-rootfs.tar.zst"
old_sha256 = "cbabff2c0aba470a54022f04b0d2d23329d7bbacdbbf2cd4005f5509964af805"
# edition 2021
# DISTRO_NAME=rust_arm64
# ROOTFS_FILE=rust_arm64_2022-10-03_03-10-rootfs.tar.zst
# SHA256SUM=109a96c2f9ddf43bb3d57827a167d2e51376e68dbb8a231b2072fbeb33a69c5f
# BUILD_DATE=20221003
# BUILD_TAG=2022-10-03
# STATUS=completed
# VERSION=latest02
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-03
begin = 2022-10-03 02:52:21.599174303+00:00
start-sync_0 = 03:00:37
start-zstd = 03:01:54
start-sync_1 = 03:09:48
end-sync_1 = 03:10:11
end = 2022-10-03 03:10:11.924912684+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-1) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (f5fed93ba 2022-09-27)'
rustc = 'rustc 1.66.0-nightly (57f097ea2 2022-10-01)'
cc = 'cc (Debian 12.2.0-4) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (f5fed93ba 2022-09-27)
release: 1.66.0-nightly
commit-hash: f5fed93ba24607980647962c59863bbabb03ce14
commit-date: 2022-09-27
host: aarch64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (57f097ea2 2022-10-01)
binary: rustc
commit-hash: 57f097ea25f2c05f424fc9b9dc50dbd6d399845c
commit-date: 2022-10-01
host: aarch64-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
