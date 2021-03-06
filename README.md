# CLX

CLX is an X11 client library for Common Lisp. The code was originally
taken from a CMUCL distribution, was modified somewhat in order to
make it compile and run under SBCL, then a selection of patches were
added from other CLXes around the net.

# Features

 - SHAPE extension support (Gilbert Baumann)
 - XFREE86-VIDMODE extension support (Iban Hatchondo)
 - experimental RENDER extension support 
     (Gilbert Baumann and Christian Sunesson)
 - X authority support that works with ssh forwarding (Eric Marsden via CMUCL)
 - OPEN-DEFAULT-DISPLAY function which, as the name suggests, does that (dan)
 - various bug fixes (Iban Hatchondo and a cast of several)
 - a manual in texinfo format (Shawn Betts, Gilbert Baumann)

# Supported versions

CLX should work with SBCL, CCL, ECL and CLISP. If it doesn't please submit an
[issue](https://github.com/sharplispers/clx/issues/new) along with the version
information of your implementation.

Allegro Common Lisp users should use clx version maintained by Franz Inc., which can
be found at [https://github.com/franzinc/clx](https://github.com/franzinc/clx)

# Building using quicklisp

```lisp
(ql:quickload 'clx)
```

or if you want to use the latest version from git, clone this repository to
your local-project and use `quickload` as described above

```shell
cd ~/quicklisp/local-projects/
git clone git://github.com/sharplispers/clx.git
```

# Building using ASDF

If you don't have quicklisp installed you can use ASDF to load CLX. To do so clone this repository to either:

* `~/.common-lisp`
* `~/.local/share/common-lisp/source/.`

where ASDF will look for system definitions by default

and then on the lisp REPL type

```lisp
(require 'asdf)
(asdf:load-system 'clx)
```

If you want to load clx from another location you have to first tell ASDF to
look in that directory by adding the directory to ASDF's central registry on every session.

```lisp
(require 'asdf)
(push "/path/to/the/clx/directory/" asdf:*central-registry*) ; Mind the trailing slash, it is important.
(asdf:load-system 'clx)
```

or you can configure ASDF to look in your directory as described in the [ASDF Manual](https://common-lisp.net/project/asdf/asdf.html#Configuring-ASDF-to-find-your-systems)


# Demos

To test CLX (and get a small amount of Lisp advocacy), try loading the file
"demo/menu", and then executing the function xlib::just-say-lisp.

```lisp
(load "clx/demo/menu")
(xlib::just-say-lisp)
```

Note: If you're new to Lisp, be advised that despite the examples in
demo/, it's generally /not/ considered good style to switch to the
:xlib package and write your code in it.  Spend some time with a
language reference to familiarize yourself with USE-PACKAGE, or 
better yet, the USE option to DEFPACKAGE.

# Contributing

To contribute submit a [pull request](https://github.com/sharplispers/clx/pulls)

To report bugs, request features, etc please use the [github issue tracker](https://github.com/sharplispers/clx/issues)

---

Heavy lifting by <Raymond.Wiker at fast.no>
ASDFized version by Daniel Barlow <dan at metacircles.com> 
and Christophe Rhodes <csr21 at cam.ac.uk>

The sharplispers group on github have recently (November 2011)
"adopted" clx and maintain the version that lives at:

https://github.com/sharplispers/clx

