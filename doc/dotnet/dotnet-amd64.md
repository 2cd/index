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
tag = ["latest", "2022-07-18", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_amd64_2022-07-18_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "593de2b8235e29526ce4433806cd9191efb401b1463f6b0edf01a5135ec7fe04"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.6G"
tar_bytes = 1703430656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "397M"
zstd_bytes = 415382755

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220704"
previous_tag = "2022-07-04"
previous_file = "dotnet_amd64_2022-07-04_12-17-rootfs.tar.zst"
previous_sha256 = "a511c1240a7e0841be8f88a3f2fe4f68430908815138984738b8c84bdbf0f344"

current_version = "latest01"
current_date = "20220718"
old_file = "dotnet_amd64_2022-06-20_12-15-rootfs.tar.zst"
old_sha256 = "33a074905be91b2f5ec66811abe282f359e25e782e5767e4ef29d6eb4043145b"
# edition 2021
# DISTRO_NAME=dotnet_amd64
# ROOTFS_FILE=dotnet_amd64_2022-07-18_12-18-rootfs.tar.zst
# SHA256SUM=593de2b8235e29526ce4433806cd9191efb401b1463f6b0edf01a5135ec7fe04
# BUILD_DATE=20220718
# BUILD_TAG=2022-07-18
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-18
begin = 2022-07-18 12:02:35.746438885+00:00
start-sync_0 = 12:06:13
start-zstd = 12:07:09
start-sync_1 = 12:17:54
end-sync_1 = 12:18:32
end = 2022-07-18 12:18:32.771054102+00:00

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
git = 'git version 2.37.1'
dotnet = '6.0.302'
powershell = 'PowerShell 7.2.5'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.302
 Commit:    c857713418

Runtime Environment:
 OS Name:     arch
 OS Version:  
 OS Platform: Linux
 RID:         arch-x64
 Base Path:   /usr/local/dotnet/sdk/6.0.302/

global.json file:
  Not found

Host:
  Version:      6.0.7
  Architecture: x64
  Commit:       0ec02c8c96

.NET SDKs installed:
  6.0.302 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 6.0.7 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 6.0.7 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Download .NET:
  https://aka.ms/dotnet-download

Learn about .NET Runtimes and SDKs:
  https://aka.ms/dotnet/runtimes-sdk-info
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
