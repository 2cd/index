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
tag = ["latest", "2022-05-16"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2022-05-16_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1f24596dfbb9cf00b31f9635a7bc6c980e31bc2ba5a0a7aec9dab3413f92d718"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "967M"
tar_bytes = 1013856256

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "206M"
zstd_bytes = 215663436

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220502"
previous_tag = "2022-05-02"
previous_file = "go_amd64_2022-05-02_12-10-rootfs.tar.zst"
previous_sha256 = "c79fb36ff3137cc6553e820dcf826031c3a550d5151dfecbffad9bb649ad7937"

current_version = "latest02"
current_date = "20220516"
old_file = "go_amd64_2022-04-18_12-11-rootfs.tar.zst"
old_sha256 = "fe1f363161bc08df58df3b24dde0df5fab4c7fd019b73d3fd9bbe0de6dad1af1"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2022-05-16_12-09-rootfs.tar.zst
# SHA256SUM=1f24596dfbb9cf00b31f9635a7bc6c980e31bc2ba5a0a7aec9dab3413f92d718
# BUILD_DATE=20220516
# BUILD_TAG=2022-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-16
begin = 2022-05-16 12:02:38.647868323+00:00
start-sync_0 = 12:04:01
start-zstd = 12:04:16
start-sync_1 = 12:09:31
end-sync_1 = 12:09:48
end = 2022-05-16 12:09:48.694618179+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
go = 'go version go1.18.2 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.2'

[other]
workdir = "/go"
```
