# go-alpine-arm64

## How to run it?

```shell
docker run \
    -it \
    --name go-alpine-arm64 \
    cake233/go-alpine-arm64
```

## How to exec shell?

```shell
    docker exec -it go-alpine-arm64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    go-alpine-arm64 \
    go build -v
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
tag = ["alpine", "2021-11-27", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "go-alpine-arm64_2021-11-27_20-31.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "fa03604bd73e3dc4b254f133723838a3a5adab8d8f23192209dcd17e8149b8ca"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "320M"
tar-bytes = 335074816

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "92M"
zstd-bytes = 96335701

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-alpine-arm64_2021-11-27_20-31.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=20:31

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 20:30:34.328944465+00:00
start-sync_0 = 20:31:05
start-zstd = 20:31:13
start-sync_1 = 20:31:32
end-sync_1 = 20:31:43
end = 2021-11-27 20:31:43.979154125+00:00

[server]
name = "docker"
node = 4
repo = "cake233/go-alpine-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "${LOCALE}"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
go = 'go version go1.17.3 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.17.3'

[other]
workdir = "/go"
```
