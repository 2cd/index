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
tag = ["latest", "2022-10-26", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_amd64_2022-10-26_00-49.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8160f7a699987ff71e1ca950ea7a8553d13dc8e240f33666097a234240206bc4"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1760634368

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "410M"
zstd_bytes = 429577248

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20221010"
previous_tag = "2022-10-10"
previous_file = "dotnet_amd64_2022-10-10_12-17-rootfs.tar.zst"
previous_sha256 = "8e823532be08982216b5bb97c083c164ecb3785a93950c1a76ab46b42c1622f5"

current_version = "latest02"
current_date = "20221026"
old_file = "dotnet_amd64_2022-09-26_12-18-rootfs.tar.zst"
old_sha256 = "23281d137adf03011a405365978c9e54f8d7b35121a28f90293a93180e21f6dd"
# edition 2021
# DISTRO_NAME=dotnet_amd64
# ROOTFS_FILE=dotnet_amd64_2022-10-26_00-49-rootfs.tar.zst
# SHA256SUM=8160f7a699987ff71e1ca950ea7a8553d13dc8e240f33666097a234240206bc4
# BUILD_DATE=20221026
# BUILD_TAG=2022-10-26
# STATUS=completed
# VERSION=latest02
# END_TIME=00:49

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-26
begin = 2022-10-26 00:33:43.103091311+00:00
start-sync_0 = 00:36:52
start-zstd = 00:37:46
start-sync_1 = 00:49:07
end-sync_1 = 00:49:59
end = 2022-10-26 00:49:59.204112817+00:00

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
dotnet = '6.0.402'
powershell = 'PowerShell 7.2.7'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.402
 Commit:    6862418796

Runtime Environment:
 OS Name:     arch
 OS Version:  
 OS Platform: Linux
 RID:         arch-x64
 Base Path:   /usr/local/dotnet/sdk/6.0.402/

global.json file:
  Not found

Host:
  Version:      6.0.10
  Architecture: x64
  Commit:       5a400c212a

.NET SDKs installed:
  6.0.402 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 6.0.10 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 6.0.10 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Download .NET:
  https://aka.ms/dotnet-download

Learn about .NET Runtimes and SDKs:
  https://aka.ms/dotnet/runtimes-sdk-info
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
