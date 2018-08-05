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

Project  | Goal
---------|-----
sound    | core sound data types, interfaces.
  sio    | portable I/O without external (non-Go, non-host) dependencies.
  codec  | a generic codec interface and implementations/adaptors.
  plug   | Providing routable real-time and offline plug-in like functionality.
  plugx  | Providing I/O interoperability with standard plugin formats such as VST and AU.
  ioval  | controllers and meters
  dsp    | transforms, convolutions, filtering

Each is hosted in its own git repository.

### Use
Our code is hosted on github under the zikichombo organisation.

```sh
go get zikichombo.org/sound...
```

Try the examples, build an app, read the code and join the discussions.


### Sponsors

We need more sponsors!  Check out our [Contributing Page](/contrib) for 
opportunities.

Sponsor | Logo
--------|-----
[IRI France, SAS](http://iri-labs.com) | ![IRI France Logo](/iri-labs.ico) 







