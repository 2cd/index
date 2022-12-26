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
tag = ["latest", "2022-12-26"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2022-12-26_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "0c5f3c913e1b2b16e3fee20e2587d039724c1658434b2d80d7562d64814aee3a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "995M"
tar_bytes = 1042413568

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "211M"
zstd_bytes = 220876493

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221212"
previous_tag = "2022-12-12"
previous_file = "go_amd64_2022-12-12_12-10-rootfs.tar.zst"
previous_sha256 = "4e2a60297b578299f201ef064c3a46c12321c664fe24c87edc0d87de9da9402a"

current_version = "latest01"
current_date = "20221226"
old_file = "go_amd64_2022-11-28_12-09-rootfs.tar.zst"
old_sha256 = "7d2c56952be4a88aae6e43d7f20f09ec6320e9042e4fae86c74c769b30a126a0"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2022-12-26_12-09-rootfs.tar.zst
# SHA256SUM=0c5f3c913e1b2b16e3fee20e2587d039724c1658434b2d80d7562d64814aee3a
# BUILD_DATE=20221226
# BUILD_TAG=2022-12-26
# STATUS=completed
# VERSION=latest01
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-26
begin = 2022-12-26 12:02:28.823004840+00:00
start-sync_0 = 12:03:47
start-zstd = 12:04:03
start-sync_1 = 12:09:15
end-sync_1 = 12:09:34
end = 2022-12-26 12:09:34.245542117+00:00

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
go = 'go version go1.19.4 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.19.4'

[other]
workdir = "/go"
```
