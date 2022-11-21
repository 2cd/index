# dotnet-amd64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/dotnet-amd64 \
    dotnet new console -o world

docker run \
    -t \
    --rm \
    -v "$TMP"/world:/app \
    -w /app \
    cake233/dotnet-amd64 \
    dotnet run --verbosity 4
```

## How to exec shell?

```sh
docker run \
    -it \
    --name dotnet-amd64 \
    cake233/dotnet-amd64
```

You can also specify the absolute path to the shell.

```sh
docker exec -it dotnet-amd64 /usr/local/powershell/pwsh
```


## dotnet-amd64.toml

```toml
[main]
name = "dotnet"
tag = ["latest", "2022-11-21", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_amd64_2022-11-21_12-15.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "d8262e7008a2e6e36db70fcaa1f4990044463730fb27844c8eb5b8c9648a8571"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1810344960

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "417M"
zstd_bytes = 436757011

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221026"
previous_tag = "2022-10-26"
previous_file = "dotnet_amd64_2022-10-26_00-49-rootfs.tar.zst"
previous_sha256 = "8160f7a699987ff71e1ca950ea7a8553d13dc8e240f33666097a234240206bc4"

current_version = "latest01"
current_date = "20221121"
old_file = "dotnet_amd64_2022-10-10_12-17-rootfs.tar.zst"
old_sha256 = "8e823532be08982216b5bb97c083c164ecb3785a93950c1a76ab46b42c1622f5"
# edition 2021
# DISTRO_NAME=dotnet_amd64
# ROOTFS_FILE=dotnet_amd64_2022-11-21_12-15-rootfs.tar.zst
# SHA256SUM=d8262e7008a2e6e36db70fcaa1f4990044463730fb27844c8eb5b8c9648a8571
# BUILD_DATE=20221121
# BUILD_TAG=2022-11-21
# STATUS=completed
# VERSION=latest01
# END_TIME=12:15

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-11-21
begin = 2022-11-21 12:02:27.703316622+00:00
start-sync_0 = 12:05:42
start-zstd = 12:06:21
start-sync_1 = 12:15:31
end-sync_1 = 12:15:59
end = 2022-11-21 12:15:59.837144747+00:00

[server]
repo = "cake233/dotnet-amd64"

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
PATH = "/usr/local/powershell:/usr/local/dotnet/bin${PATH:+:${PATH}}"
DOTNET_ROOT = "/usr/local/dotnet"
DOTNET_RUNNING_IN_CONTAINER = true
ASPNETCORE_URLS = ""
DOTNET_GENERATE_ASPNET_CERTIFICATE = false
DOTNET_USE_POLLING_FILE_WATCHER = true
Logging__Console__FormatterName = ""
NUGET_XMLDOC_MODE = "skip"

[version]
ldd = 'ldd (GNU libc) 2.36'
git = 'git version 2.38.1'
dotnet = '7.0.100'
powershell = 'PowerShell 7.3.0'
dotnet_info = '''
.NET SDK:
 Version:   7.0.100
 Commit:    e12b7af219

Runtime Environment:
 OS Name:     arch
 OS Version:  
 OS Platform: Linux
 RID:         arch-x64
 Base Path:   /usr/local/dotnet/sdk/7.0.100/

Host:
  Version:      7.0.0
  Architecture: x64
  Commit:       d099f075e4

.NET SDKs installed:
  7.0.100 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 7.0.0 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 7.0.0 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Other architectures found:
  None

Environment variables:
  DOTNET_ROOT       [/usr/local/dotnet]

global.json file:
  Not found

Learn more:
  https://aka.ms/dotnet/info

Download .NET:
  https://aka.ms/dotnet/download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
