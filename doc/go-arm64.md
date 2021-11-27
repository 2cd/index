# go-arm64

## How to run it?

```shell
docker run \
    -it \
    --name go-arm64 \
    cake233/go-arm64
```

## How to exec shell?

```shell
    docker exec -it go-arm64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    go-arm64 \
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

## go-arm64.toml

```toml
[main]
name = "go"
tag = ["latest", "2021-11-27"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "go-arm64_2021-11-27_20-13.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "9a71de3d06a8d5487545487d6e19cb10097ab401142c0bd6ff47130f4a7fadeb"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "941M"
tar-bytes = 986196480

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "271M"
zstd-bytes = 283469369

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-arm64_2021-11-27_20-13.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=20:13

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 20:10:56.854041316+00:00
start-sync_0 = 20:11:44
start-zstd = 20:12:31
start-sync_1 = 20:13:12
end-sync_1 = 20:13:34
end = 2021-11-27 20:13:34.402889691+00:00

[server]
name = "docker"
node = 4
repo = "cake233/go-arm64"

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
go = 'go version go1.17.3 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.17.3'

[other]
workdir = "/go"
```
