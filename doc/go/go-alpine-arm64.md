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
tag = ["alpine", "2023-09-04", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_arm64_2023-09-04_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "3c421364f2017c3f9178c3bf476ba53c2405de8d336b59e5f00c39cf4f87e515"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "243M"
tar_bytes = 254244864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41588901

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20230904"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2023-09-04_12-08-rootfs.tar.zst
# SHA256SUM=3c421364f2017c3f9178c3bf476ba53c2405de8d336b59e5f00c39cf4f87e515
# BUILD_DATE=20230904
# BUILD_TAG=2023-09-04
# STATUS=completed
# VERSION=latest01
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-04
begin = 2023-09-04 12:02:51.593783503+00:00
start-sync_0 = 12:04:33
start-zstd = 12:04:47
start-sync_1 = 12:08:12
end-sync_1 = 12:08:25
end = 2023-09-04 12:08:25.479304187+00:00

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
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (aarch64) Version 1.2.4'
go = 'go version go1.21.0 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.0'

[other]
workdir = "/go"
```
