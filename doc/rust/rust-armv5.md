# rust-armv5

## How to run it?

```shell
docker run \
    -it \
    --name rust-armv5 \
    cake233/rust-armv5
```

## How to exec shell?

```shell
    docker exec -it rust-armv5 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/rs-project:/app \
    -w /app \
    rust-armv5 \
    cargo b --release
```

## rust-armv5.toml

```toml
[main]
name = "rust"
tag = ["latest", "2021-11-28", "nightly", "unstable", "default", "gnu-libc"]
os = "debian"
release = "sid"
arch = "armel"
platform = "linux/arm/v5"
x11_or_wayland = false

[file]
name = "rust_armel_2021-11-28_23-15.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "1f8aa936add1c3e1de96e18e09115d9dec357a11c128b84531ce12ccbcf12638"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "964M"
tar_bytes = 1010497024

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "227M"
zstd_bytes = 237521840

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""

current_version = "latest01"
current_date = "20211128"
# edition 2021
# DISTRO_NAME=rust_armel
# ROOTFS_FILE=rust_armel_2021-11-28_23-15-rootfs.tar.zst
# BUILD_DATE=20211128
# BUILD_TAG=2021-11-28
# STATUS=completed
# VERSION=latest01
# END_TIME=23:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-11-28
begin = 2021-11-28 23:03:51.816764402+00:00
start-sync_0 = 23:10:44
start-zstd = 23:11:29
start-sync_1 = 23:15:37
end-sync_1 = 23:15:58
end = 2021-11-28 23:15:59.051171393+00:00

[server]
repo = "cake233/rust-armv5"

[server.node1]
name = "cn"
current = false
previous = true
split = false

[server.node2]
name = "us"
current = false
previous = true
split = false
part = 12

[server.node3]
name = "global"
current = false
previous = true
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
rustup = 'rustup 1.24.3 (ce5817a94 2021-05-31)'
cargo = ''
rustc = ''
cc = 'cc (Debian 11.2.0-12) 11.2.0'
cargo_verbose = '''

'''
rustc_verbose = '''

'''
```
