# go-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-arm64 \
    cake233/go-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it go-alpine-arm64 bash
```

## example

```sh
docker run \
    -t \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    -e GOOS=linux \
    -e CGO_ENABLED=0 \
    cake233/go-alpine-arm64 \
    go build -trimpath --ldflags "-s -w -buildid=" -v -o main.bin
```

## readme.go
```go
// go run readme.go
package main

import "fmt"

func main() {
	var (
		country, proxy_site string
	)

	country = "China"
	proxy_site = "https://goproxy.cn"
	fmt.Printf("If you live in\x1b[%dm %v. \x1b[0m\n", 32, country)
	fmt.Printf("Then you can run the following\x1b[%dm commands. \x1b[0m\n", 31)

	fmt.Println("go env -w GO111MODULE=on")
	fmt.Printf("go env -w GOPROXY=%v,direct\n", proxy_site)
}
```

## go-alpine-arm64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-03-21", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go-musl_arm64_2022-03-21_12-06.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "306feb5f33c231380aae0de3b9d705039d55eb2e406762bb5ed6a0c6ac054df7"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "334M"
tar_bytes = 349450752

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "78M"
zstd_bytes = 81084438

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220316"
previous_tag = "2022-03-16"
previous_file = "go-musl_arm64_2022-03-16_07-54-rootfs.tar.zst"
previous_sha256 = "3757bbdf6f54a92aa3e9cbe60bbbabb3d8070a362592bd96ef92400e96e3b900"

current_version = "latest02"
current_date = "20220321"
old_file = "go-musl_arm64_2022-03-07_12-07-rootfs.tar.zst"
old_sha256 = "d47fa8357c94a055cb298ba549ac4467da8878dd1c625e0c19c36ecd1360e8d2"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2022-03-21_12-06-rootfs.tar.zst
# SHA256SUM=306feb5f33c231380aae0de3b9d705039d55eb2e406762bb5ed6a0c6ac054df7
# BUILD_DATE=20220321
# BUILD_TAG=2022-03-21
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-21
begin = 2022-03-21 12:02:29.158469297+00:00
start-sync_0 = 12:03:30
start-zstd = 12:03:42
start-sync_1 = 12:06:36
end-sync_1 = 12:06:48
end = 2022-03-21 12:06:48.479553585+00:00

[server]
repo = "cake233/go-alpine-arm64"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (aarch64) Version 1.2.2'
go = 'go version go1.18 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18'

[other]
workdir = "/go"
```
