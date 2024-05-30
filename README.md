# asdf-erlang-prebuilt-ubuntu

Erlang plugin for [asdf](https://github.com/asdf-vm/asdf) version manager, using Erlang builds by [hexpm/bob](https://github.com/hexpm/bob), for ubuntu. Attempts to auto determine the release (18.04, 20.04, 22.04, 24.04, etc) as well as the system architecture (arm64/amd64) to install the correct one for the platform.

NOTE: `lsb_release` is used to perform automatic detection of ubuntu release
NOTE: `dpkg --print-architecture` is used to perform automatic detection of system architecture

You can override the ARCH, or Ubuntu versions (via `ImageOS`) by specifying an environment flag at `asdf install erlang ...` with the following flags:
* ImageOS
* ARCH

| ImageOS  | Operating system
|-         |-
| ubuntu18 | ubuntu-18.04
| ubuntu20 | ubuntu-20.04
| ubuntu22 | ubuntu-22.04
| ubuntu24 | ubuntu-24.04

ImageOS was selected as the environment variable to be consistent with https://github.com/erlef/setup-beam

| ARCH  
|-         
| amd64 
| arm64 

e.g. `ImageOS=ubuntu24 ARCH=amd64 asdf install erlang 26.2.5` will use the precompiled BOB build from `https://builds.hex.pm/builds/otp/amd64/ubuntu-24.04/OTP-26.2.5.tar.gz`. 

## Install

```
asdf plugin-add erlang https://github.com/cranksecurity/asdf-erlang-prebuilt-ubuntu.git
```