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
tag = ["alpine", "2023-09-18", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_amd64_2023-09-18_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "5f0c43a2fba92071c3f385e5999021c3b93b74c4cde2964247961ec3ea5861db"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "237M"
tar_bytes = 248239616

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "41M"
zstd_bytes = 42821065

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230904"
previous_tag = "2023-09-04"
previous_file = "go-musl_amd64_2023-09-04_12-07-rootfs.tar.zst"
previous_sha256 = "0720d001f4df29e1d4fbcc7962c71643035f479dd5e2f9a65e71f2101d0f9ce6"

current_version = "latest02"
current_date = "20230918"
old_file = "go-musl_amd64_2023-08-21_12-07-rootfs.tar.zst"
old_sha256 = "1332b0ba90a73cae395c92724d5fb66bf364eb35018963cd617da54a94e57a8f"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go-musl_amd64_2023-09-18_12-06-rootfs.tar.zst
# SHA256SUM=5f0c43a2fba92071c3f385e5999021c3b93b74c4cde2964247961ec3ea5861db
# BUILD_DATE=20230918
# BUILD_TAG=2023-09-18
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-09-18
begin = 2023-09-18 12:02:42.387335526+00:00
start-sync_0 = 12:03:37
start-zstd = 12:03:49
start-sync_1 = 12:06:06
end-sync_1 = 12:06:19
end = 2023-09-18 12:06:19.311098662+00:00

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
ldd = 'musl libc (x86_64) Version 1.2.4'
go = 'go version go1.21.1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.1'

[other]
workdir = "/go"
```
