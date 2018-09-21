---
title: "Premiers Pas"
author: wsc
date: 2018-09-21T19:26:29+02:00
draft: false
---

## First Steps
It has been about 7 weeks into the launch, and a lot has happened.  We've made progress
on growing our community, as well as important, encouraging, and enabling first steps
in many projects.

## Codecs
The [zc/codec](http://github.com/zikichombo/codec) project has been quietly gaining 
traction.  A general interface which allows pluggable sound codecs to easily
interoperate with I/O and processing and core sound processors has evolved to meet
demands of codec authors.  Moreover, the project supports 3rd party codecs and so 
can be used in conjunction with codecs like AAC which are out of zc scope for 
licensing reasons.

Although hidden in [zc/ext](http://github.com/zikichombo/ext), we've grown 
our codec collection to support FLAC decoding and ogg/vorbis decoding.  More
are on the way.

## Sound I/O
Sound I/O has traditionally been quite problematic for Go, and progress
here has been characterised by _alpha chaos_.  Fast forward motion and 
volatile code, as difficult as it is to follow, have enabled several key 
advances

#### Host Structuring
An portable code layout enabling multiple host specific implementations 
has been put in place, as well as a means for 3rd parties to write
and distribute interfaces to host drivers independently.  Although the code
is still _alpha_ and some details of the interface are still likely to change over
time, the big picture is a huge step toward the goal of effective sound I/O
with host only dependencies and the overall organisation of the host structuring
is unlikely to change in the near future.  This work comes with a new
[porting guide](https://github.com/zikichombo/sio/blob/master/Porting.md)
and so the project is well positioned to become a widely ported and used
sound I/O package for Go.

#### Reliabality
Go, as well as any non-C based language, has a terrible reputation for 
reliability in the case of mass marketed low latency applications.  This
is the case even when using very seriously engineered and established projects
like [portaudio](http://portaudio.com) via cgo.  ZikiChombo has pushed 
forward on this issue, engaging [portaudio](https://lists.columbia.edu/pipermail/portaudio/2018-September/001508.html)  and [golang developers](https://groups.google.com/forum/#!topic/golang-dev/EVwSXv8JTsk)  to help clarify
the root causes, and we have arrived at some proposed solutions.  For
example, the addition of [rb](https://github.com/zikichombo/sio/blob/master/libsio/rb.md)
is a first _draft_ design of a means to bypass the various problems 
behind low latency reliability on un-dedicated hardware for sound i/o with Go.

## DSP
The DSP code base has grown some documentation and clarity, and the first 
[dsp-star](https://github.com/zikichombo/dsp/issues?utf8=✓&q=is%3Aissue+label%3Adsp-star)
labelled issue has been fixed, giving zc/dsp its build badge.

The DSP code base has also grown a [resample package](http://godoc.org/zikichombo.org/dsp/resample)
which enables monotonic continuous time views of PCM data, dynamic resampling, and 
control over resampling quality.

Some progress has also been made offline on the infamous [half-complex issue](https://github.com/zikichombo/dsp/issues/1),
So we're looking forward to that becoming a non-blocker for advancing on some
higher level dsp functionality in the near future.

## Mel Support
The [zc/sound](http://godoc.org/zikichombo.org/sound) project also grew support 
for the Mel frequency scale interoperating with the frequency type.  This is 
a simple addition that is also key to enabling higher level music dsp functionality
down the road.

## Licensing and Community
In the first steps of our first weeks, it has become evident that a plethora
of open source licenses and associated repositories are the norm.  As an old 
guy, I had thought things would be more readily organisable by a single shared
author license.  I was wrong; and ZikiChombo has made several procedural steps to 
build the community and enable a simple licensing solution for consumers
(That means no vendering).

First, zc has arranged code so that in many cases, import direction can work
both ways between collaboraters.  This is a valuable asset for code
organisation, allow direct code contributions and 3rd party distributions.

Second zc has created a special [zc/ext](http://github.com/zikichombo/ext) 
module which can import both 3rd party code and the rest of zc. This is
a playground which can facilitate collaboration.

Finally, zc has [decided to](https://github.com/zikichombo/meta/issues/6)
relicense its code base under the Apache 2.0 license to work with more
other projects without introducing licensing multiplicity, and to afford
some standard open source patent protection as well.


## Conclusion
Our first steps are indeed exciting.  We've got a long way to go, and a lot
of work to do.  But major progress has indeed been made on many fronts.

Thanks to all the ZikiChombo members, collaborators, discussions and
the general culture of mutual respect between open source projects, without
which probably none of our _premiers pas_ could have been made.


