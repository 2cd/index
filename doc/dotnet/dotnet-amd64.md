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
tag = ["latest", "2022-05-09", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_amd64_2022-05-09_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a6c7fefa6832983f5aefb0033a6025ca2f393d9fb95e2154a5b3a9ff8cdb9062"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1673416192

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "394M"
zstd_bytes = 412535424

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220425"
previous_tag = "2022-04-25"
previous_file = "dotnet_amd64_2022-04-25_12-16-rootfs.tar.zst"
previous_sha256 = "3a36740d7faa0f62ca8bd2a6fe02b6ec2a46cca3945f342b489d6dbb05aa09b5"

current_version = "latest02"
current_date = "20220509"
old_file = "dotnet_amd64_2022-04-11_11-15-rootfs.tar.zst"
old_sha256 = "200c4888fe0e18430a4042be8c1ace8c62b3fee06be60d0705aa230109be630a"
# edition 2021
# DISTRO_NAME=dotnet_amd64
# ROOTFS_FILE=dotnet_amd64_2022-05-09_12-18-rootfs.tar.zst
# SHA256SUM=a6c7fefa6832983f5aefb0033a6025ca2f393d9fb95e2154a5b3a9ff8cdb9062
# BUILD_DATE=20220509
# BUILD_TAG=2022-05-09
# STATUS=completed
# VERSION=latest02
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-09
begin = 2022-05-09 12:02:36.201167662+00:00
start-sync_0 = 12:06:05
start-zstd = 12:07:04
start-sync_1 = 12:17:57
end-sync_1 = 12:18:35
end = 2022-05-09 12:18:35.978386206+00:00

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
ldd = 'ldd (GNU libc) 2.35'
git = 'git version 2.36.1'
dotnet = '6.0.202'
powershell = 'PowerShell 7.2.3'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.202
 Commit:    f8a55617d2

Runtime Environment:
 OS Name:     arch
 OS Version:  
 OS Platform: Linux
 RID:         arch-x64
 Base Path:   /usr/local/dotnet/sdk/6.0.202/

Host (useful for support):
  Version: 6.0.4
  Commit:  be98e88c76

.NET SDKs installed:
  6.0.202 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 6.0.4 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 6.0.4 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

To install additional .NET runtimes or SDKs:
  https://aka.ms/dotnet-download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
