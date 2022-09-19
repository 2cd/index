# rust-ppc64le

## How to run it?

```sh
docker run \
    -it \
    --name rust-ppc64le \
    cake233/rust-ppc64le
```

## How to exec shell?

```sh
docker exec -it rust-ppc64le bash
```
<!-- repo=cake233/rust-ppc64le -->

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
    cake233/rust-ppc64le \
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
    cake233/rust-ppc64le \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-ppc64le.toml

```toml
[main]
name = "rust"
tag = ["latest", "2022-09-19", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-09-19_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0cb7a8709b3a8133d0db2f0889ca2f6130a5d546e80004fc4b99e2f4271e8c25"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1779426304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "247M"
zstd_bytes = 258009385

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220916"
previous_tag = "2022-09-16"
previous_file = "rust_ppc64el_2022-09-16_03-05-rootfs.tar.zst"
previous_sha256 = "a0a7d77909dc416b8e74831d36bd1aaa465b29821a2be434ea182fa2842835e6"

current_version = "latest01"
current_date = "20220919"
old_file = "rust_ppc64el_2022-09-12_03-05-rootfs.tar.zst"
old_sha256 = "9828958f225897a41872926042da750daae6fe9d5b6ec1e9945745cb69bb971f"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-09-19_03-05-rootfs.tar.zst
# SHA256SUM=0cb7a8709b3a8133d0db2f0889ca2f6130a5d546e80004fc4b99e2f4271e8c25
# BUILD_DATE=20220919
# BUILD_TAG=2022-09-19
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-19
begin = 2022-09-19 02:52:22.662809184+00:00
start-sync_0 = 02:58:53
start-zstd = 02:59:51
start-sync_1 = 03:05:28
end-sync_1 = 03:05:50
end = 2022-09-19 03:05:50.552586466+00:00

[server]
repo = "cake233/rust-ppc64le"

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
ldd = 'ldd (Debian GLIBC 2.34-8) 2.34'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (082503982 2022-09-13)'
rustc = 'rustc 1.66.0-nightly (a37499ae6 2022-09-18)'
cc = 'cc (Debian 12.2.0-2) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (082503982 2022-09-13)
release: 1.66.0-nightly
commit-hash: 082503982ea0fb7a8fd72210427d43a2e2128a63
commit-date: 2022-09-13
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (a37499ae6 2022-09-18)
binary: rustc
commit-hash: a37499ae66ec5fc52a93d71493b78fb141c32f6b
commit-date: 2022-09-18
host: powerpc64le-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.0
'''
```
