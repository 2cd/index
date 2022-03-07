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
tag = ["alpine", "2022-03-07", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go-musl_arm64_2022-03-07_12-07.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "d47fa8357c94a055cb298ba549ac4467da8878dd1c625e0c19c36ecd1360e8d2"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "334M"
tar_bytes = 349257728

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "78M"
zstd_bytes = 81054117

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "go-musl_arm64_2022-03-01_18-57-rootfs.tar.zst"
previous_sha256 = "34c5318f67d2f7d1507b0606a068b16cdeca3c56555a1f727f7491eb0d8a8056"

current_version = "latest02"
current_date = "20220307"
old_file = "go-musl_arm64_2022-02-07_12-05-rootfs.tar.zst"
old_sha256 = "b48e88c048378cc2129b78cfdf8acc8eb47815bff814e56ca463c03683ac60a0"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2022-03-07_12-07-rootfs.tar.zst
# SHA256SUM=d47fa8357c94a055cb298ba549ac4467da8878dd1c625e0c19c36ecd1360e8d2
# BUILD_DATE=20220307
# BUILD_TAG=2022-03-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-07
begin = 2022-03-07 12:02:37.308341650+00:00
start-sync_0 = 12:03:41
start-zstd = 12:03:54
start-sync_1 = 12:07:18
end-sync_1 = 12:07:31
end = 2022-03-07 12:07:31.446414702+00:00

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
go = 'go version go1.18rc1 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18rc1'

[other]
workdir = "/go"
```
