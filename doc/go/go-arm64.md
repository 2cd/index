# go-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-arm64 \
    cake233/go-arm64
```

## How to exec shell?

```sh
docker exec -it go-arm64 bash
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
    cake233/go-arm64 \
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

## go-arm64.toml

```toml
[main]
name = "go"
tag = ["latest", "2024-01-15"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2024-01-15_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "78c43ea539757005f7fc80ab787f99c5435c19c89c387bc73e8148ef337727a6"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "836M"
tar_bytes = 876286464

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "159M"
zstd_bytes = 166632148

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20240115"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2024-01-15_12-10-rootfs.tar.zst
# SHA256SUM=78c43ea539757005f7fc80ab787f99c5435c19c89c387bc73e8148ef337727a6
# BUILD_DATE=20240115
# BUILD_TAG=2024-01-15
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-15
begin = 2024-01-15 12:02:35.956151547+00:00
start-sync_0 = 12:05:13
start-zstd = 12:05:27
start-sync_1 = 12:09:50
end-sync_1 = 12:10:05
end = 2024-01-15 12:10:05.567261358+00:00

[server]
repo = "cake233/go-arm64"

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
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
go = 'go version go1.21.6 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.6'

[other]
workdir = "/go"
```
