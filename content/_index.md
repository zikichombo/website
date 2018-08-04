ZikiChombo is an open source project for a simple, reliable, and efficient 
sound processing and I/O library in [Go](http://golang.org).

ZikiChombo is in alpha, not yet appropriate for production use.

# Scope
Sound processing and I/O encompasses a vast landscape of functionality, touching
on digital signal processing, "firm" real time processing where failures to
meet deadlines renders applications useless rather than degraded.  ZikiChombo
does not aim to provide support a full coverage of this landscape alone.  Rather,
ZikiChombo aims to be an enabler for developers, an effective library for low and
high level applications which interoperate nicely.

To this end, ZikiChombo has the following sub-projects

Project | Goal
--------|-----
Core    | Providing simple composable interfaces and implementations which enable streaming, processing, and controlling sound in real time or offline.
IO      | Providing portable I/O without external (non-Go) dependencies such as portaudio/rtAudio.
Plug    | Providing I/O interoperability with standard plugin formats such as VST and AU.
Codecs  | Providing a generic codec interface and implementations/adaptors.
DSP     | Providing DSP and filtering support.
Muziki  | Music information retrieval.

# Use
Our code is hosted on github under the zikichombo organisation.

```sh
go get github.com/zikichombo...
```

Try the examples, build an app.

# Sponsor us
We have sponsorship programs, the ability to earmark features, and the ability for
developers to be paid by sponsorship.  We engage in FOSS development for the quality 
of the resulting software, not as free labor for enterprises.  We ask that if you 
use our products for profit, then you contribute in a fair and reasonable way proportional
to your budget and what ZikiChombo provides therein.  Sponsorship offers some possible
[ways of contributing](/contrib).









