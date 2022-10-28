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
tag = ["latest", "2022-10-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-10-28_03-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7952e3513129e9039823584b5a51910a22fe24c889cd0a2f60d07c50eec28d36"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1749634048

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "241M"
zstd_bytes = 251825433

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221024"
previous_tag = "2022-10-24"
previous_file = "rust_ppc64el_2022-10-24_03-10-rootfs.tar.zst"
previous_sha256 = "b97599c384afc43a2d709322ec93b284620822d3ea1aa91d2e2b7700e7c8e4eb"

current_version = "latest02"
current_date = "20221028"
old_file = "rust_ppc64el_2022-10-21_03-32-rootfs.tar.zst"
old_sha256 = "9585c8fb648ba1885830f9e31f9ebcf244d6011cf5fd439b37372120f3f81958"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-10-28_03-05-rootfs.tar.zst
# SHA256SUM=7952e3513129e9039823584b5a51910a22fe24c889cd0a2f60d07c50eec28d36
# BUILD_DATE=20221028
# BUILD_TAG=2022-10-28
# STATUS=completed
# VERSION=latest02
# END_TIME=03:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-28
begin = 2022-10-28 02:52:24.362334551+00:00
start-sync_0 = 02:58:53
start-zstd = 02:59:56
start-sync_1 = 03:05:39
end-sync_1 = 03:05:59
end = 2022-10-28 03:05:59.816939891+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-4) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (9210810d1 2022-10-25)'
rustc = 'rustc 1.66.0-nightly (0da281b60 2022-10-27)'
cc = 'cc (Debian 12.2.0-7) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (9210810d1 2022-10-25)
release: 1.66.0-nightly
commit-hash: 9210810d1fd7b51ae0439a0a363cc50e36963455
commit-date: 2022-10-25
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (0da281b60 2022-10-27)
binary: rustc
commit-hash: 0da281b6068a7d889ae89a9bd8991284cc9b7535
commit-date: 2022-10-27
host: powerpc64le-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
