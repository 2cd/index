# rust-mips64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-mips64le \
    cake233/rust-mips64le
```

## How to exec shell?

```sh
docker exec -it rust-mips64le bash
```
<!-- repo=cake233/rust-mips64le -->

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
    cake233/rust-mips64le \
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
    cake233/rust-mips64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-mips64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-06-27", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "mips64el"
platform = "linux/mips64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_mips64el_2022-06-27_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b8a26ed19ab20a7bf05725ff4f4229f9c83e2b2ed9cb3c55fc80eb1c24c44418"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1671504896

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "210M"
zstd_bytes = 220020182

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220624"
previous_tag = "2022-06-24"
previous_file = "rust_mips64el_2022-06-24_03-05-rootfs.tar.zst"
previous_sha256 = "5565cdba2a47c566542131fa672ccbe3de49fc26a020e19e6f48bf0de43e34cf"

current_version = "latest02"
current_date = "20220627"
old_file = "rust_mips64el_2022-06-20_03-07-rootfs.tar.zst"
old_sha256 = "e215f0db00dc8e9dbc67ddf4cd2e23aeb2725b2dd6a9ce0960366166c6bdbda2"
# edition 2021
# DISTRO_NAME=rust_mips64el
# ROOTFS_FILE=rust_mips64el_2022-06-27_03-05-rootfs.tar.zst
# SHA256SUM=b8a26ed19ab20a7bf05725ff4f4229f9c83e2b2ed9cb3c55fc80eb1c24c44418
# BUILD_DATE=20220627
# BUILD_TAG=2022-06-27
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-27
begin = 2022-06-27 02:52:28.924104082+00:00
start-sync_0 = 02:58:40
start-zstd = 02:59:39
start-sync_1 = 03:04:43
end-sync_1 = 03:05:03
end = 2022-06-27 03:05:03.972371018+00:00

[server]
repo = "cake233/rust-mips64le"

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
cargo = 'cargo 1.64.0-nightly (a5e08c470 2022-06-23)'
rustc = 'rustc 1.64.0-nightly (c80c4b8fd 2022-06-26)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.64.0-nightly (a5e08c470 2022-06-23)
release: 1.64.0-nightly
commit-hash: a5e08c4703f202e30cdaf80ca3e7c00baa59c496
commit-date: 2022-06-23
host: mips64el-unknown-linux-gnuabi64
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.64.0-nightly (c80c4b8fd 2022-06-26)
binary: rustc
commit-hash: c80c4b8fdcf3da69cd483e2fec172c9b1f95842c
commit-date: 2022-06-26
host: mips64el-unknown-linux-gnuabi64
release: 1.64.0-nightly
LLVM version: 14.0.5
'''
```
