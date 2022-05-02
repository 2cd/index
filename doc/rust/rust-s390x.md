# rust-s390x

## How to run it?

```sh
docker run \
    -it \
    --name rust-s390x \
    cake233/rust-s390x
```

## How to exec shell?

```sh
docker exec -it rust-s390x bash
```
<!-- repo=cake233/rust-s390x -->

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
    cake233/rust-s390x \
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
    cake233/rust-s390x \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-s390x.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-05-02", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2022-05-02_03-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3df1782cd97c7cada15f2972f11d756eacd5e725e4a91d7b3e21b6a90f053a21"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1777767936

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "245M"
zstd_bytes = 256437429

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220429"
previous_tag = "2022-04-29"
previous_file = "rust_s390x_2022-04-29_03-05-rootfs.tar.zst"
previous_sha256 = "95c741c5602da0bbeb5562cf6d672e1c78634e166097a107c28aed59ef9207d0"

current_version = "latest02"
current_date = "20220502"
old_file = "rust_s390x_2022-04-25_03-07-rootfs.tar.zst"
old_sha256 = "d9fdd0f11800d0c57e2cae97eb5d47a72374238d94033144f38794883543a4d0"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2022-05-02_03-06-rootfs.tar.zst
# SHA256SUM=3df1782cd97c7cada15f2972f11d756eacd5e725e4a91d7b3e21b6a90f053a21
# BUILD_DATE=20220502
# BUILD_TAG=2022-05-02
# STATUS=completed
# VERSION=latest02
# END_TIME=03:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-02
begin = 2022-05-02 02:52:25.657632694+00:00
start-sync_0 = 02:58:49
start-zstd = 02:59:56
start-sync_1 = 03:06:18
end-sync_1 = 03:06:38
end = 2022-05-02 03:06:38.047494647+00:00

[server]
repo = "cake233/rust-s390x"

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
cargo = 'cargo 1.62.0-nightly (f63f23ff1 2022-04-28)'
rustc = 'rustc 1.62.0-nightly (4dd8b420c 2022-05-01)'
cc = 'cc (Debian 11.3.0-1) 11.3.0'
cargo_verbose = '''
cargo 1.62.0-nightly (f63f23ff1 2022-04-28)
release: 1.62.0-nightly
commit-hash: f63f23ff1f1a12ede8585bbd1bbf0c536e50293d
commit-date: 2022-04-28
host: s390x-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.80.0-DEV (sys:0.4.51+curl-7.80.0 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.62.0-nightly (4dd8b420c 2022-05-01)
binary: rustc
commit-hash: 4dd8b420c027001e47b0d811a7e55e2fe1de1395
commit-date: 2022-05-01
host: s390x-unknown-linux-gnu
release: 1.62.0-nightly
LLVM version: 14.0.1
'''
```
