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
tag = ["latest", "2022-10-24", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "ppc64el"
platform = "linux/ppc64le"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_ppc64el_2022-10-24_03-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "b97599c384afc43a2d709322ec93b284620822d3ea1aa91d2e2b7700e7c8e4eb"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1747963392

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "241M"
zstd_bytes = 251868292

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221021"
previous_tag = "2022-10-21"
previous_file = "rust_ppc64el_2022-10-21_03-32-rootfs.tar.zst"
previous_sha256 = "9585c8fb648ba1885830f9e31f9ebcf244d6011cf5fd439b37372120f3f81958"

current_version = "latest01"
current_date = "20221024"
old_file = "rust_ppc64el_2022-10-17_03-06-rootfs.tar.zst"
old_sha256 = "46eb88fa9be0d8f3fcf39c3fe862354e053e7039f6b954134eef46ad8f99c27f"
# edition 2021
# DISTRO_NAME=rust_ppc64el
# ROOTFS_FILE=rust_ppc64el_2022-10-24_03-10-rootfs.tar.zst
# SHA256SUM=b97599c384afc43a2d709322ec93b284620822d3ea1aa91d2e2b7700e7c8e4eb
# BUILD_DATE=20221024
# BUILD_TAG=2022-10-24
# STATUS=completed
# VERSION=latest01
# END_TIME=03:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-24
begin = 2022-10-24 02:52:24.581756719+00:00
start-sync_0 = 03:02:04
start-zstd = 03:03:13
start-sync_1 = 03:10:07
end-sync_1 = 03:10:31
end = 2022-10-24 03:10:31.867795795+00:00

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
ldd = 'ldd (Debian GLIBC 2.35-3) 2.35'
rustup = 'rustup 1.25.1 (bb60b1e89 2022-07-12)'
cargo = 'cargo 1.66.0-nightly (071eeaf21 2022-10-22)'
rustc = 'rustc 1.66.0-nightly (7fcf850d7 2022-10-23)'
cc = 'cc (Debian 12.2.0-7) 12.2.0'
cargo_verbose = '''
cargo 1.66.0-nightly (071eeaf21 2022-10-22)
release: 1.66.0-nightly
commit-hash: 071eeaf210708219a5a1b2c4728ca2f97df7f2ae
commit-date: 2022-10-22
host: powerpc64le-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (7fcf850d7 2022-10-23)
binary: rustc
commit-hash: 7fcf850d7942804990a1d2e3fe036622a0fe4c74
commit-date: 2022-10-23
host: powerpc64le-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
