---
title: "Projects"
date: 2018-08-03T19:26:43+02:00
viz: true
---

### Overview

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
  plugx->sound
  plugx->sio
  plug->sound
  plug->ioval
  ioval->sound
  }
```

Our development roadmap follows dependency order.  The less dependent 
projects are the most mature.  Our bandwidth for advancing depends on
your support and engagement.

## Rough status and development order

The sound project is close to beta, and should be usable for 
prototyping and testing products set for production in the near future.

The sio project is alpha-level-functional for darwin and linux/ALSA.  Other
platforms (ios android freebsd ..) are in varying states of readiness.  For
example, ios support closely follows darwin support and the actual i/o
shouldn't be much work at all, but it also requires audio sessions
configuration which we haven't yet started to address.  Android is a bit more
complicated but also should be able to make use of the ALSA driver atleast in
theory.  In general, Duplex i/o interfaces are more likely to change than
capture/playback.

The codec project has some solid codecs (eg wav), but the generic codec
interface is still being hashed out.

The ioval project is in discussion/proposal stage.

The plug project is in a "probably" late alpha state, interfaces
can change but the design and principles remain.

the plugx project is in discussion/proposal stage.

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

All of our projects have a strong bias towards eliminating C dependencies,
except for code with operating system level audio support.  ALSA is at the
limit in that it is in the linux kernel and also a separate C library.  Any
non-Go library not provided with the base operating system with kernel level
support is not in our interest to incorporate.

Given ffmpeg and friends, This may hurt for a while, but it will pay off.  In
the meantime, since apple has OS-level support for sound codecs, we are
considering taking advantage of that.

## Repositories and Code Hosting
Each project P is hosted at github.com/zikichombo/P.

Each project makes use of github releases, semantic version tags,
github issue tracking and pull requests.

The issue tracker is our best tool for keeping track of technical discussions
so feel free to file an issue if only to discuss some technical aspect
of the respective project.

## Code of Conduct
We're not so into regulating behavior but we will be firm about 
requesting respectful dialogue geared toward project and organisation goals.

Some things to keep in mind are that newcomers opinions and questions
are extremely valuable in achieving simplicity.  By default, the responsability 
for newcomer confusion is on the project and organisation shoulders.  It 
doesn't help to point them to some dark corner in a maze of documentation and
issues, implying they should have seen that and spent months or years reading 
everything before asking. The question could well have come up because we weren't 
clear or organised enough.







