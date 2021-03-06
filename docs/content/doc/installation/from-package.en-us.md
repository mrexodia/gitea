---
date: "2016-12-01T16:00:00+02:00"
title: "Installation from package"
slug: "install-from-package"
weight: 10
toc: true
draft: false
menu:
  sidebar:
    parent: "installation"
    name: "From package"
    weight: 20
    identifier: "install-from-package"
---

# Installation from package

## Debian

The only distribution that has any "official" package of Gitea is Debian. This is currently
in Debian's [contrib](https://wiki.debian.org/SourcesList). This is (currently) only available
in Debian testing and unstable (but should be installable/functional on stable).

- Edit /etc/apt/sourced.list
   - Add "contrib" to "deb http://deb.debian.org/debian unstable main contrib"
- apt-get update
- apt-get install gitea

For other distributions, see the [deployment from binary]({{< relref "from-binary.en-us.md" >}}) guide.

## Windows

There are no published packages for Windows. This page will change when packages are published,
in the form of `MSI` installers or via [Chocolatey](https://chocolatey.org/). In the meantime
the [deployment from binary]({{< relref "from-binary.en-us.md" >}}) guide.

## macOS

Currently, the only supported method of installation on MacOS is [Homebrew](http://brew.sh/).
Following the [deployment from binary]({{< relref "from-binary.en-us.md" >}}) guide may work,
but is not supported. To install Gitea via `brew`:

```
brew tap go-gitea/gitea
brew install gitea
```

## FreeBSD

A FreeBSD port `www/gitea` is available. To install the pre-built binary package:

```
pkg install gitea
```

For the most up to date version, or to build the port with custom options,
[install it from the port](https://www.freebsd.org/doc/handbook/ports-using.html):

```
su -
cd /usr/ports/www/gitea
make install clean
```

The port uses the standard FreeBSD file system layout: config files are in `/usr/local/etc/gitea`,
bundled templates, options, plugins and themes are in `/usr/local/share/gitea`, and a start script
is in `/usr/local/etc/rc.d/gitea`.

To enable Gitea to run as a service, run `sysrc gitea_enable=YES` and start it with `service gitea start`.
