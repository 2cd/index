# rust-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name rust-alpine-amd64 \
    cake233/rust-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it rust-alpine-amd64 bash
```
<!-- repo=cake233/rust-alpine-amd64 -->

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
    cake233/rust-alpine-amd64 \
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
    cake233/rust-alpine-amd64 \
    cargo b --release
```

### check file

```sh
FILE="tmp/hello/target/release/hello"

file "$FILE"
ldd "$FILE"
```

## rust-alpine-amd64.toml

```toml
[main]
name = "rust"
tag = ["alpine", "2022-10-24", "nightly", "unstable", "minimal", "musl-libc", "musl"]
os = "alpine"
release = "edge"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "rust-musl_amd64_2022-10-24_03-00.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "4c87d2944e23fbcd1bb66b96ffdcae8bf0d3044b3ebaca1005372e77a46e4a4e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "808M"
tar_bytes = 847024128

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "163M"
zstd_bytes = 170703977

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221021"
previous_tag = "2022-10-21"
previous_file = "rust-musl_amd64_2022-10-21_02-59-rootfs.tar.zst"
previous_sha256 = "b8ccc82a2070348689099d6a45404a9e50c7456641a712565905fc16572bdc68"

current_version = "latest01"
current_date = "20221024"
old_file = "rust-musl_amd64_2022-10-17_02-58-rootfs.tar.zst"
old_sha256 = "fba03aae975a1a0618aea4c1f9ac05d5886ff4ec0b3639f136f4046dc912bdea"
# edition 2021
# DISTRO_NAME=rust_amd64
# ROOTFS_FILE=rust-musl_amd64_2022-10-24_03-00-rootfs.tar.zst
# SHA256SUM=4c87d2944e23fbcd1bb66b96ffdcae8bf0d3044b3ebaca1005372e77a46e4a4e
# BUILD_DATE=20221024
# BUILD_TAG=2022-10-24
# STATUS=completed
# VERSION=latest01
# END_TIME=03:00

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-24
begin = 2022-10-24 02:52:27.100360135+00:00
start-sync_0 = 02:53:25
start-zstd = 02:54:12
start-sync_1 = 02:59:46
end-sync_1 = 03:00:05
end = 2022-10-24 03:00:06.006732268+00:00

[server]
repo = "cake233/rust-alpine-amd64"

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
LANG = "C.UTF-8"
PATH = "/usr/local/cargo/bin${PATH:+:${PATH}}"
RUSTUP_HOME = "/usr/local/rustup"
CARGO_HOME = "/usr/local/cargo"

[version]
ldd = 'musl libc (x86_64) Version 1.2.3'
rustup = 'rustup 1.25.1 (2022-07-12)'
cargo = 'cargo 1.66.0-nightly (071eeaf21 2022-10-22)'
rustc = 'rustc 1.66.0-nightly (7fcf850d7 2022-10-23)'
cc = 'cc (Alpine 12.2.1_git20220924-r3) 12.2.1 20220924'
cargo_verbose = '''
cargo 1.66.0-nightly (071eeaf21 2022-10-22)
release: 1.66.0-nightly
commit-hash: 071eeaf210708219a5a1b2c4728ca2f97df7f2ae
commit-date: 2022-10-22
host: x86_64-unknown-linux-musl
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Alpine Linux 3.17_alpha20220715 [64-bit]
'''
rustc_verbose = '''
rustc 1.66.0-nightly (7fcf850d7 2022-10-23)
binary: rustc
commit-hash: 7fcf850d7942804990a1d2e3fe036622a0fe4c74
commit-date: 2022-10-23
host: x86_64-unknown-linux-musl
release: 1.66.0-nightly
LLVM version: 15.0.2
'''
```
