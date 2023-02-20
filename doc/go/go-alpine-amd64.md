# go-alpine-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-amd64 \
    cake233/go-alpine-amd64
```

## How to exec shell?

```sh
docker exec -it go-alpine-amd64 bash
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
    cake233/go-alpine-amd64 \
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

## go-alpine-amd64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2023-02-20", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2023-02-20_12-05.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ef041c2804f6d7a12b43fa8abaf03b0c65d9a5076eec1ae010183fe2a9e87999"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "268M"
tar_bytes = 280497152

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "73M"
zstd_bytes = 75968718

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230206"
previous_tag = "2023-02-06"
previous_file = "go-musl_amd64_2023-02-06_12-06-rootfs.tar.zst"
previous_sha256 = "096d2202f0a724379429d3caa0892150d75325fcb64c8b088bece829370687fc"

current_version = "latest02"
current_date = "20230220"
old_file = "go-musl_amd64_2023-01-23_12-07-rootfs.tar.zst"
old_sha256 = "8b44ba665622983c367df1ee8b6992c2e7e01a9e2138262df0e3db1ba128f16c"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2023-02-20_12-05-rootfs.tar.zst
# SHA256SUM=ef041c2804f6d7a12b43fa8abaf03b0c65d9a5076eec1ae010183fe2a9e87999
# BUILD_DATE=20230220
# BUILD_TAG=2023-02-20
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-20
begin = 2023-02-20 12:02:31.320917117+00:00
start-sync_0 = 12:03:06
start-zstd = 12:03:14
start-sync_1 = 12:05:43
end-sync_1 = 12:05:52
end = 2023-02-20 12:05:52.264003811+00:00

[server]
repo = "cake233/go-alpine-amd64"

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
ldd = 'musl libc (x86_64) Version 1.2.3'
go = 'go version go1.20.1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.1'

[other]
workdir = "/go"
```
