<p align="center"><img width="50%" src="docs/static_files/cli-artwork.png" /></p>

<p align="center">
  <a href="https://circleci.com/gh/scaleway/scaleway-cli/tree/v2"><img src="https://circleci.com/gh/scaleway/scaleway-cli/tree/v2.svg?style=shield" alt="CircleCI" /></a>
  <a href="https://goreportcard.com/report/github.com/scaleway/scaleway-cli"><img src="https://goreportcard.com/badge/scaleway/scaleway-cli" alt="GoReportCard" /></a> <!-- GoReportCard do not support branches. -->
</p>

# Scaleway CLI (v2)

If you are looking for Scaleway CLI v1, [you can find it on the v1 branch](https://github.com/scaleway/scaleway-cli/tree/v1).

Scaleway is a single way to create, deploy and scale your infrastructure in the cloud. We help thousands of businesses to run their infrastructures easily.

If you are looking for a stable version, [see the version 1](https://github.com/scaleway/scaleway-cli/tree/master).

# Installation

<!--- TODO:
## With a Package Manager (Recommended)

A package manager allows to install and upgrade the Scaleway CLI with a single command. We recommend this installation mode for more simplicity and reliability. We support a growing set of package managers to feat your preferences and your platform. Note that some package managers are maintained by our community:

### Homebrew

Install the latest stable release on macOS using [Homebrew](http://brew.sh): _Comming soon..._

```sh
brew install scw
```

### Chocolatey

Install the lastest stable release on Windows using [Chocolatey](https://chocolatey.org/): _Coming soon..._

```powershell
choco install scaleway-cli
```

### Others

TODO: Add other package managers:
- [Chocolate](https://chocolatey.org/packages/scaleway-cli/)
- [AUR](https://aur.archlinux.org/packages/scaleway-cli/)
- [Snap](https://snapcraft.io/)
- [Apt](https://wiki.debian.org/Apt)
-->

## Manually

### Released Binaries

We provide [static-compiled binaries](https://github.com/scaleway/scaleway-cli/releases/latest) for [darwin (macOS)](#mac-os), [GNU/Linux](#linux), and [Windows](#windows) platforms.
You just have to download the binary compatible with your platform to a directory available in your [`PATH`](https://en.wikipedia.org/wiki/PATH_(variable)):

#### Mac OS

```bash
# Check that /usr/local/bin is in your PATH
$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

# Download the release from github
<<<<<<< HEAD
curl -o /usr/local/bin/scw -L "https://github.com/scaleway/scaleway-cli/releases/download/v2.0.0-beta.4/scw-2-0-0-beta-4-darwin-x86_64"
=======
$ curl -o /usr/local/bin/scw -L "https://github.com/scaleway/scaleway-cli/releases/download/v2.0.0-beta.2/scw-2-0-0-beta-2-darwin-x86_64"
>>>>>>> ce4a3001... Content

# Allow executing file as program
$ chmod +x /usr/local/bin/scw

# Init the CLI
$ scw init
```

#### Linux

```bash
# Download the release from github
<<<<<<< HEAD
sudo curl -o /usr/local/bin/scw -L "https://github.com/scaleway/scaleway-cli/releases/download/v2.0.0-beta.4/scw-2-0-0-beta-4-linux-x86_64"
=======
$ sudo curl -o /usr/local/bin/scw -L "https://github.com/scaleway/scaleway-cli/releases/download/v2.0.0-beta.2/scw-2-0-0-beta-2-linux-x86_64"
>>>>>>> ce4a3001... Content

# Allow executing file as program
$ sudo chmod +x /usr/local/bin/scw

# Init the CLI
$ scw init
```

#### Windows

You can download the last release here: https://github.com/scaleway/scaleway-cli/releases/download/v2.0.0-beta.4/scw-2-0-0-beta-4-windows-x86_64.exe<br/>
[This official guide](https://docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/ee537574%28v%3Doffice.14%29) explains how to add tools to your `PATH`.

<!-- TODO:

### Debian

First, download [the `.deb` file](https://github.com/scaleway/scaleway-cli/releases/latest) compatible with your architecture:

```bash
export ARCH=amd64 # Can be 'amd64', 'arm', 'arm64' or 'i386'
wget "https://github.com/scaleway/scaleway-cli/releases/download/v2.0.0-beta.4/scw-v2-0-0-beta-4-${ARCH}.deb" -O /tmp/scw.deb
```

Then, run the installation and remove the `.deb` file:
```bash
dpkg -i /tmp/scw.deb && rm -f /tmp/scw.deb
```
-->

<!-- TODO:
## With a Docker Image

### Official releases (Coming soon..)

For each release, we deliver a tagged image on the [Scaleway Docker Hub](https://hub.docker.com/r/scaleway/cli/tags) so can run `scw` in a sandboxed way: _Coming soon..._

```sh
docker run scaleway/cli version
```
-->

## Docker Image

You can use the CLI as you would run any Docker image:

```sh
<<<<<<< HEAD
docker run -i --rm scaleway/cli:v2.0.0-beta.4
=======
$ docker run -i --rm scaleway/cli:v2.0.0-beta.2
>>>>>>> ce4a3001... Content
```

See more in-depth information about running the CLI in Docker [here](./docs/docker.md)

## Build it yourself

### Build Locally

If you have a >= [Go 1.13](https://golang.org/) environment, you can install the `HEAD` version to test the latest features or to [contribute](CONTRIBUTING.md).
Note that this development version could include bugs, use [tagged releases](https://github.com/scaleway/scaleway-cli/releases/latest) if you need stability.

```bash
go get github.com/scaleway/scaleway-cli/cmd/scw
```

Dependencies: We only use go [Go Modules](https://github.com/golang/go/wiki/Modules) with vendoring.

### Build with Docker

You can build the `scw` CLI with Docker. If you have Docker installed, you can run:

```sh
docker build -t scaleway/cli .
```

Once build, you can then use the CLI as you would run any image:

```sh
docker run -i --rm scaleway/cli
```

See more in-depth information about running the CLI in Docker [here](./docs/docker.md)


# Getting Started

After you [installed](#Installation) the latest release just run the initialization command and let yourself be guided! :dancer:

```bash
$ scw init
```

It will set up your profile, the authentication, and the auto-completion.


# Examples

# Instances 

Cloud instances are available for any workload from 1 to 48 vCPUs with an x86 architecture. Most common apps and distributions can be deployed in seconds.

### Listing the available offers 

To see a list of available cloud instances, run the following command: 

```
$ scw instance server-type list
```

### Creating a compute instance

To create a instance in the FR-PAR-1 zone with the commercial offer DEV1-S, running on Ubuntu Focal run the following command: 
```
$ scw instance server create type=DEV1-S image=ubuntu_focal zone=fr-par-1 tags.0="scw-cli"
```

## Listing all running instances

It is possible to retrieve a list of all instances available in the account by running the following command: 
```
$ scw instance server list
``` 

###  Creating a Placement Group

Placement groups allow the user to express a preference regarding the physical position of a group of instances. It enables the user to choose to either group instances on the same physical hardware for best network throughput and low latency, or to spread instances on far away equipment to reduce the risk of physical failure.

The operating mode is selected by a `policy_type`. Two policy types are available:
  - `low_latency` will group instances on the same hypervisors
  - `max_availability` will spread instances on far away hypervisors

The `policy_type` is set by default to `max_availability`.

For each policy type, one of the two `policy_mode` may be selected:
  - `optional` will start your instances even if the constraint is not respected
  - `enforced` guarantee that if the instance starts, the constraint is respected

The `policy_mode` is set by default to `optional`.

USAGE:
```
$  scw instance placement-group <command>
```

Available commands are: 
  * `list`        List placement groups
  * `create`      Create placement group
  * `get`         Get placement group
  * `update`      Update placement group
  * `delete`      Delete the given placement group

For example, to create a placement group called `low-latency-pg` with enforced policy mode and low latency policy type in the zone `fr-par-1`, run the following command: 
```
$ scw instance placement-group create name=low-latency-pg policy-mode=enforced policy-type=low_latency zone=fr-par-1
```

# Tutorials

TODO: Add a list of tutorials here.

# Development

This repository is at its early stage and is still in active development.
If you are looking for a way to contribute please read [CONTRIBUTING.md](CONTRIBUTING.md).

# Reach Us

We love feedback.
Don't hesitate to open a [Github issue](https://github.com/scaleway/scaleway-cli/issues/new) or
feel free to reach us on [Scaleway Slack community](https://slack.scaleway.com/),
we are waiting for you on [#opensource](https://scaleway-community.slack.com/app_redirect?channel=opensource).
