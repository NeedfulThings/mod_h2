
#mod_h[ttp]2 - http/2 for Apache httpd

Copyright (C) 2015 greenbytes GmbH

This repository contains the `mod_h[ttp]2` for Apache httpd. It enables the HTTP2
protocol inside the server, using nghttp2 (https://nghttp2.org) as base engine.

##Status
**Officially an Apache httpd module**, first released in 2.4.17. See [Apache downloads](https://httpd.apache.org/download.cgi) to get a released version.

What you find here are **early experience versions** for people who like living on the edge and want to help me test not yet released changes.

If you want HTTP/2 in your production environment, please head over to the official releases at Apache and grab one of those or wait until the various OS distributions have assembled one for you. 

##Current Version
The version here is the **Proposed backport to 2.4.x**, to be published hopefully as 2.4.18. 

This is therefore an **early experience version**
and there is no guarantee that it will be released as it is here by Apache. But you are welcome to test it and give feedback.

Notice that this version builds in ```sandbox```mode by default when you give no arguments to ```configure```. That is so, because several people tried to compile it against a release Apache httpd. That does not work however, as patches to httpd core are necessary. Luckily, these are applied automatically to the sandbox built.


##OS Packages

* **Ubuntu**: [ppa by ondrej](https://launchpad.net/~ondrej/+archive/ubuntu/apache2) for Ubuntu 14.04 and others
* **Fedora**: [Rawhide includes httpd 2.4.17](http://rpmfind.net/linux/rpm2html/search.php?query=httpd)
* **Debian** sid (unstable) includes httpd 2.4.17. See [how to install debian sid](https://wiki.debian.org/InstallFAQ#Q._How_do_I_install_.22unstable.22_.28.22sid.22.29.3F)
* **FreeBSD**: [sp1l has been working on ports](https://github.com/Sp1l/ports)


##Documenation
There is the official [Apache documentation](https://httpd.apache.org/docs/2.4/en/mod/mod_http2.html) of the module, which you will not find here.

I also compiled a [how to h2 in apache](https://icing.github.io/mod_h2/howto.html) document with advice on how to deploy, configure and verify your ```mod_h[ttp]2``` installation.

##Build from git
Still not dissuaded? Ok, here are some hints to get you started.
Building from git is easy, but please be sure that at least autoconf 2.68 is
used:

```
> autoreconf -i
> automake
> autoconf
> ./configure
> make
```


##Licensing
Please see the file called LICENSE.


##Credits
This work has been funded by the GSM Association (http://gsma.com). The module
itself was heavily influenced by mod_spdy, the Google implementation of their
SPDY protocol. And without Tatsuhiro Tsujikawa excellent nghttp2 work, this
would not have been possible.


Münster, 05.11.2015,

Stefan Eissing, greenbytes GmbH

Copying and distribution of this file, with or without modification,
are permitted in any medium without royalty provided the copyright
notice and this notice are preserved.  This file is offered as-is,
without warranty of any kind. See LICENSE for details.


