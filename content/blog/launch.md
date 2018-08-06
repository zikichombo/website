---
title: "Launch!"
author: wsc
---

## Launching zikichombo 

We have decided to launch ZikiChombo after careful consideration of our own
private work and several interesting public go audio projects, discussions, and
proposals.

### Background.

In 2015, [Rakyll](http://github.com/rakyll)
[proposed](https://github.com/golang/go/issues/13432).  audio I/O in the scope
of the go mobile project.  This project has sparked a lot of interest amongst
gophers, giving rise to the shiny interface for example.  The scope of the
proposal was in our opinion a bit too focused on Android and Go access to
mobile apps, and decided to use openal as the backing component.

OpenAL is a gaming library which considers playback and recording "extensions"
and features 3d rendering.  It is implemented on iOS and darwin on top of
apples AudioUnits.  It was originally sponsored by SoundBlaster.  On Linux, it
is built on top of ALSA.  It's API is notoriously difficult and very not
Go-like.

In 2017 [Matt Aimonetti](http://github.com/mattetti)
[proposed](https://github.com/golang/go/issues/18497) an audio package for Go.
Perhaps the first pioneer to put Go to commercial use related to sound at
[Splice](http://splice.com) and with a background as an audio engineer and
music producer, his perspective on Go and audio is quite different, driven by
both production needs and lots of experience working with sound software. This
led to the [Go Audio Github](http://github.com/go-audio) organisation which is
a noble effort to consolidate audio for Go.

The work above has been happily ignored by
[Oto](https://github.com/hajimehoshi/oto) which provides an output interface on
top of openal, alsa, and works for android and ios.

This work has also been happily ignored by the very interesting
[Beep](https://github.com/faiface/beep) which brings some nifty image know-how
to audio.

Also worth mentioning as a point of reference is [This ALSA
driver](https://github.com/yobert/alsa) which manages to directly talk to the
linux kernel level ALSA without the library.

There are [A myriad](https://golanglibs.com/search?q=sound&sort=top) of 
other projects, some of which surely deserve mention here.

All of these projects are innovative, bold, and very much struggling by comparison
to to say AudioUnits, VSTs, JUCE, etc.  They are struggling because this is uncharted territory
and all "the experts" are doing things for ProTools, LogicPro, Audible, etc, at least most
of them in a very non-Go like way, most notably with a seeming fervour for unsimplicity.
They are also struggling because they simply wrap other C projects, like portaudio
supercollider, etc.

### The Need
Go is a perfectly capable programming language I guess about a decade old now,
and brings with it a lot of plan9 and inferno related technology, IP, and
practical computer science giants.  Lots of folks, including yours truly, have
thought and will continue to think "hey lets do audio in Go", and maybe
moreover really in Go, not via wrappers. Many will also think lets do so with
commercial grade reliability.  

Frankly, this was a delusion which nearly ended my financial independence.
Others are out there playing and recording on dozens of platforms and dozens of
codecs and having their work automatically hosted as VSTs and AudioUnits
readily integrated into dozens of widely used DAWs, synths, etc.  I wanted to
do some new things, had some successes and failures and many rounds of putting
my foot in my mouth with DSP know-how [^1].  I believe my successes would be on
the market and used if I had not chosen my favorite langage, Go.

Instead, the best I could offer anyone was "uh here's a wave file and some darwin i/o
and text output and if you measure the results, they are good".

The fundamental problem was lack of libraries and lack of interoperability of libraries.
I had underestimated the role of the software language ecosystem in the field.

This problematic touches on all developers.  It also makes work like Oto and
Beep quite interesting.  They are 1-person projects which accomplish a lot and 
show successful interdependence.  But they are far from a basis on which to turn
for audio support because the functionality is very incomplete.  They serve more
like proof of concepts with very narrow general applicability.  

I think all of us would like to be able to do input and output, sometimes
duplex in a way which interacts with codecs, processing, operations and
controllers on a variety of common platforms.  Moreover, not addressing all
this with a global eye on composability will inevitably render simplicity
_unattainable_ due to dependency and integration overhead.  

We can't have simple composability accross the levels of codecs, I/O and
processing _without_ cool projects like Oto and Beep, because we wouldn't have
enough working examples to make wise choices about composability without their
work.  But we also cannot rely on these projects to evolve with higher level
composability outside of their scope in mind.

There is a need to address this, and an open source community has the potential
to do so in a long lasting reliable way.

### What should happen
Go needs to nail the architecture to be useful in this domain.  Unfortunately,
it doesn't seem that Google in all its might is doing what it takes to get
there.  For one thing the Core Gophers don't have audio in their culture.  For
another, Go invites fresh ways of approaching problems by taking the software
engineering approach, which implicitly often devalues domain expertise in favor
of the authority of plain ol CS smarts.  While that works well in some
contexts, Audio processing is too deep mathematically, scientifically, and
culturally for this.  The CS smarts needs to remain respectfully in service of
the end goals here.

### Problems are Opportunities.
This problem presents us with many opportunities.  It presents us with an
opportunity to take open source sound and audio to a new level, a level
functionally competitive with the experts, which are by and very large not open
source.  It presents us with an opportunity for a huge variety of audio and
sound based cloud processing, a topic where the "experts" tend to be lacking in
culture gophers tend to have.  It presents us with an opportunity to be bring
unprecedented simplicity to sound and audio software work, which in turn
presents us with an opportunity to disrupt the field with an open source
culture doing highly advanced and creative audio work with grace, ease,
simplicity, and as developers who design and implement programs rather than
confounding very unsimple framework know-how with expertise.

From echo cancellation on a speakerphones to polyphonic pitch detection and
real-time-voice-mapping, or 3d mixing with convolutional reverb configured for
all source and listener positions in virtualized space for very high quality
audio rendering, _we_ can make it happen here.

### Community
For any open source project to succeed, it needs a community.  ZikiChombo is not about
Google, or Android vs Apple, or Scott Cotton's DSP/SE prowess.  It is about you engaging in these 
opportunities as a user, a reader, a guiding member, an investor or donor in a way 
which furthers our bottom line:

_ZikiChombo is an open source project dedicated to providing a simple, reliable, and efficient sound
processing and I/O library in [Go](http://golang.org)._

If you are an audio developer interested in contributing your work or know-how
to this goal, ZikiChombo is a friendly, productive place to engage.  If you're
consistently involved enough in the topic yourself,  consider becoming a member.
[email us](mailto:membership@zikichombo.org).

### Back to work
Enough manifesto trumpeting.  Time to get back to the code.  See ya, respectfully,
in the forums.


[^1]: As a bonafied PhD in applied mathematics without former DSP experience, I found this journey deep, interesting, and learnable.  I speak hence not as a bonafied DSP expert but rather as someone who takes the time to do the proofs and learn the relevant terminology and notation and to try crazy practically useless variations like inversing FFT inversion to see when it breaks things, just to learn how it works.
