# go-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-amd64 \
    cake233/go-amd64
```

## How to exec shell?

```sh
docker exec -it go-amd64 bash
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
    cake233/go-amd64 \
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

## go-amd64.toml

```toml
[main]
name = "go"
tag = ["latest", "2023-02-06"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2023-02-06_12-08.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ae3a228ba33779936a060b8b30908a33e9418e098feb33e8a54d61de9a533cba"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "789M"
tar_bytes = 827062784

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "183M"
zstd_bytes = 191824792

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230123"
previous_tag = "2023-01-23"
previous_file = "go_amd64_2023-01-23_12-10-rootfs.tar.zst"
previous_sha256 = "d9523d59d814db190c4c64b37283b7f72eda4a49ef24c5c367ebccb4b886c02c"

current_version = "latest02"
current_date = "20230206"
old_file = "go_amd64_2023-01-09_12-12-rootfs.tar.zst"
old_sha256 = "89d5cbe1fc7cf46f0a3194fb86b259364bfd44de610feaaee1c278c662f361ea"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2023-02-06_12-08-rootfs.tar.zst
# SHA256SUM=ae3a228ba33779936a060b8b30908a33e9418e098feb33e8a54d61de9a533cba
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 12:02:30.480435091+00:00
start-sync_0 = 12:03:15
start-zstd = 12:03:28
start-sync_1 = 12:07:45
end-sync_1 = 12:08:01
end = 2023-02-06 12:08:01.050724697+00:00

[server]
repo = "cake233/go-amd64"

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
LANG = "en_US.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
go = 'go version go1.20 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.20'

[other]
workdir = "/go"
```
