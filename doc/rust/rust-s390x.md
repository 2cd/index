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
tag = ["latest", "2023-07-07", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "s390x"
platform = "linux/s390x"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust_s390x_2023-07-07_03-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "c21736b72de9ffdbaa4d74d171ff306de0ca78b5595d9b81cdc70f9e7298c831"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1880822272

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "238M"
zstd_bytes = 248942547

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230703"
previous_tag = "2023-07-03"
previous_file = "rust_s390x_2023-07-03_03-10-rootfs.tar.zst"
previous_sha256 = "151eba224e0e87080f2cbeb8a657a47d65e53c8211df797ebc28db90480ee740"

current_version = "latest02"
current_date = "20230707"
old_file = "rust_s390x_2023-06-30_03-06-rootfs.tar.zst"
old_sha256 = "1fc43eb184cfb114a86366b3b84385d6e388ec5c4e309065afa61df1fed9561d"
# edition 2021
# DISTRO_NAME=rust_s390x
# ROOTFS_FILE=rust_s390x_2023-07-07_03-07-rootfs.tar.zst
# SHA256SUM=c21736b72de9ffdbaa4d74d171ff306de0ca78b5595d9b81cdc70f9e7298c831
# BUILD_DATE=20230707
# BUILD_TAG=2023-07-07
# STATUS=completed
# VERSION=latest02
# END_TIME=03:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-07-07
begin = 2023-07-07 02:52:33.852928863+00:00
start-sync_0 = 02:59:08
start-zstd = 03:00:22
start-sync_1 = 03:07:22
end-sync_1 = 03:07:45
end = 2023-07-07 03:07:45.558951547+00:00

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
ldd = 'ldd (Debian GLIBC 2.37-4) 2.37'
rustup = 'rustup 1.26.0 (5af9b9484 2023-04-05)'
cargo = 'cargo 1.72.0-nightly (5b377cece 2023-06-30)'
rustc = 'rustc 1.72.0-nightly (85bf07972 2023-07-06)'
cc = 'cc (Debian 12.3.0-5) 12.3.0'
cargo_verbose = '''
cargo 1.72.0-nightly (5b377cece 2023-06-30)
release: 1.72.0-nightly
commit-hash: 5b377cece0e0dd0af686cf53ce4637d5d85c2a10
commit-date: 2023-06-30
host: s390x-unknown-linux-gnu
libgit2: 1.6.4 (sys:0.17.2 vendored)
libcurl: 8.1.2-DEV (sys:0.4.63+curl-8.1.2 vendored ssl:OpenSSL/1.1.1u)
ssl: OpenSSL 1.1.1u  30 May 2023
os: Linux [64-bit]
'''
rustc_verbose = '''
rustc 1.72.0-nightly (85bf07972 2023-07-06)
binary: rustc
commit-hash: 85bf07972a1041b9e25393b803d0e006bec3eaaf
commit-date: 2023-07-06
host: s390x-unknown-linux-gnu
release: 1.72.0-nightly
LLVM version: 16.0.5
'''
```
