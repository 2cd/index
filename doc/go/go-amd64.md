# go-amd64

## How to run it?

```shell
docker run \
    -it \
    --name go-amd64 \
    cake233/go-amd64
```

## How to exec shell?

```shell
    docker exec -it go-amd64 bash
```

## example

```shell
docker run \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    cake233/go-amd64 \
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

## go-amd64.toml

```toml
[main]
name = "go"
tag = ["latest", "2021-12-08"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "go_amd64_2021-12-08_01-12.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "8cb91f8903a793724020ef1faa6b7975fa141d225b31dcd0ef660d6e2cbcfa92"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "944M"
tar_bytes = 989412864

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "222M"
zstd_bytes = 232316143

[compatibility]
compatible_mode = true

last_version = "latest01"

# The value is &str, not int
last_date = "20211129"
last_tag = "2021-11-29"
last_file = "go_amd64_2021-11-29_00-30-rootfs.tar.zst"
last_sha256 = ""

current_version = "latest02"
current_date = "20211208"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2021-12-08_01-12-rootfs.tar.zst
# SHA256SUM=8cb91f8903a793724020ef1faa6b7975fa141d225b31dcd0ef660d6e2cbcfa92
# BUILD_DATE=20211208
# BUILD_TAG=2021-12-08
# STATUS=completed
# VERSION=latest02
# END_TIME=01:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-08
begin = 2021-12-08 01:06:13.611604582+00:00
start-sync_0 = 01:07:19
start-zstd = 01:07:39
start-sync_1 = 01:11:41
end-sync_1 = 01:12:04
end = 2021-12-08 01:12:04.787577138+00:00

[server]
repo = "cake233/go-amd64"

[server.node1]
name = "cn"
current = false
last = true
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
last = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
last = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "en_US.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
go = 'go version go1.17.4 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.17.4'

[other]
workdir = "/go"
```
