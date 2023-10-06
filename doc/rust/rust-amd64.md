# rust-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-amd64 \
    cake233/rust-amd64
```

## How to exec shell?

```sh
docker exec -it rust-amd64 bash
```
<!-- repo=cake233/rust-amd64 -->

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
    cake233/rust-amd64 \
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
    cake233/rust-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-amd64.toml

```toml
[main]
name = "rust"
tag = ["latest", "2023-10-06", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_amd64_2023-10-06_03-01.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "18ef69651669b1e6317524db0f320e3210cc87ed8c863cd58e387fdda6ac7d30"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1618320896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "214M"
zstd_bytes = 223976515

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231002"
previous_tag = "2023-10-02"
previous_file = "rust_amd64_2023-10-02_02-59-rootfs.tar.zst"
previous_sha256 = "025d0608bbda05297da4f8599d351e998768dc2dbcebf758da2ba333b74c9d76"

current_version = "latest02"
current_date = "20231006"
old_file = "rust_amd64_2023-09-29_03-01-rootfs.tar.zst"
old_sha256 = "605fd62f4fd71db0a527f75303c3023b946ee9ae89ab68068ece9b3066bb1477"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust_amd64_2023-10-06_03-01-rootfs.tar.zst
# SHA256SUM=18ef69651669b1e6317524db0f320e3210cc87ed8c863cd58e387fdda6ac7d30
# BUILD_DATE=20231006
# BUILD_TAG=2023-10-06
# STATUS=completed
# VERSION=latest02
# END_TIME=03:01

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-10-06
begin = 2023-10-06 02:52:39.531377119+00:00
start-sync_0 = 02:54:48
start-zstd = 02:55:52
start-sync_1 = 03:01:10
end-sync_1 = 03:01:34
end = 2023-10-06 03:01:34.781162462+00:00

[server]
repo = "cake233/rust-amd64"

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
ldd = 'ldd (Debian GLIBC 2.37-12) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.75.0-nightly (794d0a825 2023-10-03)'
rustc = 'rustc 1.75.0-nightly (cae0791da 2023-10-05)'
cc = 'cc (Debian 13.2.0-4) 13.2.0'
cargo_verbose = '''
cargo 1.75.0-nightly (794d0a825 2023-10-03)
release: 1.75.0-nightly
commit-hash: 794d0a82547f3081044c0aca7b6083733ce51344
commit-date: 2023-10-03
host: x86_64-unknown-linux-gnu
libgit2: 1.7.1 (sys:0.18.1 vendored)
libcurl: 8.3.0-DEV (sys:0.4.66+curl-8.3.0 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Debian [64-bit]
'''
rustc_verbose = '''
rustc 1.75.0-nightly (cae0791da 2023-10-05)
binary: rustc
commit-hash: cae0791da47bb01f16885eb233dcd66b0093a6e1
commit-date: 2023-10-05
host: x86_64-unknown-linux-gnu
release: 1.75.0-nightly
LLVM version: 17.0.2
'''
```
