ZikiChombo is an open source project dedicated to providing a simple, reliable, and efficient 
sound processing and I/O library in [Go](http://golang.org).

All the ZikiChombo projects are in alpha, not yet appropriate for production use.
Some are well ahead of others.  Check out the [projects](/projects) page for
inter-project dependencies and project roadmaps.

### Scope
Sound processing and I/O encompasses a vast landscape of functionality, touching
on digital signal processing, "firm" real time processing where failures to
meet deadlines renders applications useless rather than degraded.  ZikiChombo
does not aim to provide support a full coverage of this landscape alone.  Rather,
ZikiChombo aims to be an enabler for developers, an effective library for low and
high level applications which interoperate nicely.

To this end, ZikiChombo has the following sub-projects

Project  | Goal | GoDoc
---------|------|------
[sound](http://github.com/zikichombo/sound)    | core sound data types, interfaces. | [doc](http://godoc.org/zikichombo.org/sound)
  [sio](http://github.com/zikichombo/sio)    | portable I/O without external (non-Go, non-host) dependencies.| [doc](http://godoc.org/zikichombo.org/sio)
  [codec](http://github.com/zikichombo/codec)  | a generic codec interface and implementations/adaptors.| [doc](http://godoc.org/zikichombo.org/codec)
  [dsp](http://github.com/zikichombo/dsp)    | transforms, convolutions, filtering | [doc](http://godoc.org/zikichombo.org/dsp)
  [plug](http://github.com/zikichombo/plug)   | Providing routable real-time and offline plug-in like functionality. | docs not yet available.
  [plugx](http://github.com/zikichombo/plugx)  | Providing I/O interoperability with standard plugin formats such as VST and AU. | docs not yet available
  [ioval](http://github.com/zikichombo/ioval)  | controllers and meters | docs not yet available

Each is hosted in its own git repository.

### Use
Our code is hosted on github under the zikichombo organisation.

```sh
go get zikichombo.org/sound
go get zikichombo.org/sio
go get zikichombo.org/codec
go get zikichombo.org/dsp
```

Try the examples, build an app, read the code and join the discussions.  The remaining projects
(ioval, plug, plugx) are not yet go-gettable, feel free to join in on the design/discussion phase on github.


### Sponsors

We need more sponsors!  Check out our [Contributing Page](/contrib) for 
opportunities.

Sponsor | Logo
--------|-----
[IRI France, SAS](http://iri-labs.com) | ![IRI France Logo](/iri-labs.ico) 







