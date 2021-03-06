---
title: "Projects"
date: 2018-08-03T19:26:43+02:00
viz: true
---

## Overview

The following table summarizes the projects.

Project  | Goal | GoDoc
---------|------|------
[sound](http://github.com/zikichombo/sound)    | core sound data types, interfaces. | [doc](http://godoc.org/zikichombo.org/sound)
  [sio](http://github.com/zikichombo/sio)    | portable I/O without external (non-Go, non-host) dependencies.| [doc](http://godoc.org/zikichombo.org/sio)
  [codec](http://github.com/zikichombo/codec)  | a generic codec interface and implementations/adaptors.| [doc](http://godoc.org/zikichombo.org/codec)
  [dsp](http://github.com/zikichombo/dsp)    | transforms, convolutions, filtering | [doc](http://godoc.org/zikichombo.org/dsp)
  [plug](http://github.com/zikichombo/plug)   | Providing routable real-time and offline plug-in like functionality. | [doc](http://godoc.org/zikichombo.org/plug)
  [plugx](http://github.com/zikichombo/plugx)  | Providing I/O interoperability with standard plugin formats such as VST and AU. | docs not yet available
  [ioval](http://github.com/zikichombo/ioval)  | controllers and meters | docs not yet available


## Inter-project dependencies.

ZikiChombo projects have the following dependencies
```viz-dot
  digraph g { 
  sound[label="sound"]
  sio[label="sio"]
  plug[label="plug"]
  plugx[label="plugx"]
  dsp[label="dsp"]
  ioval[label="ioval"]
  codec[label="codec"]

  dsp->plug
  plug->sound
  sio->sound
  codec->sound
  codec->dsp
  plugx->sound
  plugx->sio
  plug->ioval
  ioval->sound
  }
```

## Rough status and development order
Our development roadmap follows dependency order.  The less dependent projects
are the most mature.  Note that the dependencies above are coarse-grained, and
the dependency order of development is not necessarily so.  Our bandwidth for
advancing depends on your [support and engagement](/contrib/).  


#### sound
The sound project is close to beta, and should be usable for 
prototyping and testing products set for production in the near future.

#### sio
The sio project is alpha-level-functional for darwin and linux/ALSA.  Other
platforms (ios android freebsd ..) are in varying states of readiness.  For
example, ios support closely follows darwin support and the actual i/o
shouldn't be much work at all, but it also requires audio sessions
configuration which we haven't yet started to address.  Android is a bit more
complicated but also should be able to make use of the ALSA driver atleast in
theory.  In general, Duplex i/o interfaces and device datatypes are more likely 
to change than capture/playback.

#### codec
The codec project has some solid codecs (eg wav), but the generic codec
interface [is still being hashed out](https://github.com/zikichombo/codec/issues/3). 

#### ioval
The ioval project is in [discussion/proposal](https://github.com/zikichombo/ioval/issues/1) 
stage.

#### plug
The plug project is in a "probably" late alpha state, interfaces
can change but the design and principles remain.

#### plugx
the plugx project is in [discussion/proposal](https://github.com/zikichombo/plugx/issues/1) 
stage.

#### dsp
the dsp project has lots of independent beta-mature code for FFT,
convolution, etc.  The interfaces and relationships to plug project
are under examination for real-time/streaming use.

## Sound Plugs
We have a number of sound processing plugins which have served
as test cases for designing the core interfaces here.  These
are projects which have worked in the past and are waiting for
the core projects here to mature for publication.  They are in 
our attic, waiting to come out.  Examples include onset detection,
pitch tracking, timescale modification, and acoustic steel string guitar 
polyphonic pitch detection.

We hope to create an ecosystem of Go sound processing plugs provided
with the project and by third parties.  However, we estimate 
the most efficient path to getting this working simply, reliably, and
efficiently is to wait until the plug interface settles into beta.


## Guidelines

At a high level, of our projects have a strong bias towards eliminating C dependencies,
except for code with host operating system level audio support.  Within that space,
we prefer to restrict the code to be as close to the kernel as possible.  For example,
pulseaudio we can interface, but we should prefer to address ALSA first.  In this 
way, Go projects can more easily compete with pulseaudio and consumers of ZikiChombo
can still use it if they wish.  We are not interested in code such as portaudio or ffmpeg
which are projects external to the base host operating system.

This may hurt for a while, but it will pay off.  In the meantime, since apple has OS-level 
support for sound codecs, we are considering taking advantage of that.

For detailed description of guidelines and project dependences, please see
[meta](http://github.com/zikichombo/meta).

## Repositories and Code Hosting
Each project P is hosted at github.com/zikichombo/P.

Each project makes use of github releases, semantic version tags,
github issue tracking and pull requests, and go modules.

The issue tracker is our best tool for keeping track of technical discussions
so feel free to file an issue if only to discuss some technical aspect
of the respective project.

## Code of Conduct
As it's early, we only assert that we will be firm about requesting respectful
dialogue geared toward project and organisation goals.  We are considering
adopting a policy of accepting a list of standard codes of conduct for as long
as you engage in the project, so as _not_ to reserve the right to unilaterally
change the code of conduct, as doing so would disempower those engaging in the
project.

In the event you encounter difficulties, please try to work them out peacefully 
offline.  If this is not really possible, mail us at conduct@zikichombo.org.

One thing we would like to guarantee on our end is that newcomers opinions and
questions are extremely valuable in achieving simplicity.  By default, the
responsability for newcomer confusion is on the project and organisation
shoulders.  It doesn't help to point them to some dark corner in a maze of
documentation and issues, implying they should have seen that and spent months
or years reading everything before asking. The question could well have come up
because we weren't clear or organised enough.






