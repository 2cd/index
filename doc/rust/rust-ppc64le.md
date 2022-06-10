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
tag = ["latest", "2022-06-10", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-06-10_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "80ef25be80a30d0b6cdbd73d8da811d8c11bfaad9c8bcbc346452553e78668ca"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1731307008

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "233M"
zstd_bytes = 243673797

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220606"
previous_tag = "2022-06-06"
previous_file = "rust_ppc64el_2022-06-06_03-10-rootfs.tar.zst"
previous_sha256 = "a7e2f0a70d3e877c86aad6b5016ff57509c7e0b78d8a221732c5b7293d0e4724"

current_version = "latest01"
current_date = "20220610"
old_file = "rust_ppc64el_2022-06-03_03-07-rootfs.tar.zst"
old_sha256 = "c4a6b3e0868234777ee4e42a9f3364a71c7f956ad2f8e67fa8a5aba13cb083e3"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-06-10_03-05-rootfs.tar.zst
# SHA256SUM=80ef25be80a30d0b6cdbd73d8da811d8c11bfaad9c8bcbc346452553e78668ca
# BUILD_DATE=20220610
# BUILD_TAG=2022-06-10
# STATUS=completed
# VERSION=latest01
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-10
begin = 2022-06-10 02:52:27.495079834+00:00
start-sync_0 = 02:58:54
start-zstd = 02:59:50
start-sync_1 = 03:05:03
end-sync_1 = 03:05:44
end = 2022-06-10 03:05:44.260834109+00:00

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
ldd = 'ldd (Debian GLIBC 2.33-7) 2.33'
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = 'cargo 1.63.0-nightly (4d92f07f3 2022-06-09)'
rustc = 'rustc 1.63.0-nightly (420c970cb 2022-06-09)'
cc = 'cc (Debian 11.3.0-3) 11.3.0'
cargo_verbose = '''
cargo 1.63.0-nightly (4d92f07f3 2022-06-09)
release: 1.63.0-nightly
commit-hash: 4d92f07f34ba7fb7d7f207564942508f46c225d3
commit-date: 2022-06-09
host: powerpc64le-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.63.0-nightly (420c970cb 2022-06-09)
binary: rustc
commit-hash: 420c970cb1edccbf60ff2aeb51ca01e2300b09ef
commit-date: 2022-06-09
host: powerpc64le-unknown-linux-gnu
release: 1.63.0-nightly
LLVM version: 14.0.5
'''
```
