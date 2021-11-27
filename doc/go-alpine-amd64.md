# go-alpine-amd64

## How to run it?

```shell
docker run \
    -it \
    --name go-alpine-amd64 \
    cake233/go-alpine-amd64
```

## How to exec shell?

```shell
    docker exec -it go-alpine-amd64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    go-alpine-amd64 \
    go build -v
```

## README.go
```go
// go run README.go
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

## build info

```toml
[main]
name = "go"
tag = ["alpine", "2021-11-27", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
nogui = true

# If the value is false, then the container will not be downloaded.
completed = true

[file]
name = "go-alpine-amd64_2021-11-27_19-50.tar.zst"

version = "0.0.0-alpha.1"

# This value can be used to verify the integrity of the file
sha256 = "dd5e0202e544e3854b76015f69fbb167b0d7f6ee05f31b055f5263c883939a71"

# zstd: [1-22]
zstd-level = 13

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "323M"
tar-bytes = 338339328

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "98M"
zstd-bytes = 102103052

[compatibility]
compatible_mode = true
rootfs_version = "latest02"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-alpine-amd64_2021-11-27_19-50.tar.zst
# BUILD_DATE=20211127
# STATUS=completed
# VERSION=latest02
# END_TIME=19:50

[time]
format = "rfc-3339"
zone = "UTC"
begin = 2021-11-27 19:49:05.357015853+00:00
start-sync_0 = 19:49:26
start-zstd = 19:49:35
start-sync_1 = 19:49:51
end-sync_1 = 19:50:04
end = 2021-11-27 19:50:04.293435687+00:00

[server]
name = "docker"
node = 4
repo = "cake233/go-alpine-amd64"

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
