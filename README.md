# Scripts and Utilities for the Microsoft Docker Registry

This repository contains scripts and REST API definitions for the Microsoft Docker image Repository located at https://mcr.microsoft.com/v2/

## REST Client HTTP samples

The [`mcr.microsoft.com.http`](mcr.microsoft.com.http) file contains smaple REST API endpoints that can be called against the docker registry. It follows the semantics of the [Docker Registry API specification](https://docs.docker.com/registry/spec/api/).

The HTTP file is a http-request file format for the VS Code REST Client extension.

## PowerShell script

The [`mcr.microsoft.com.ps1`](mcr.microsoft.com.ps1) script contains PowerShell utility commandlets for interacting with the Microsoft Docker Registry.

The script only contains function declarations, it can safely be sourced into a PowerShell session.

``` ps1
. ./mcr.microsoft.com.ps1
```

### Get-McrImageReferenceManifest function

The `Get-McrImageReferenceManifest` commandlet returns a Docker Image Manifest object as a `PSCustomObject`. If present the `v1Compatibility` property is converted from JSON and replaces the `history` property that conatains it.

The `created` and `os.version` properties in the `history` object are converted to a `datetimeoffset` and `version` instance respectively.
