# My personal knowledge base

This is a collection of articles, talks, books, and other resources I've come across over the years. The vast majority should be stuff I actually read or watched, it's not just a bookmarking service.

This document is very much a work in progress, most of my links are still to be added. At one point I'll probably split it into multiple documents.

## Development

### Performance

- Instructions can be essentially free if you're waiting for your memory to catch up
  - [dotGo 2016 - Damian Gryski - Slices: Performance through cache-friendliness](https://www.youtube.com/watch?v=jEG4Qyo_4Bc&feature=share)
  - [CppCon 2016: Timur Doumler “Want fast C++? Know your hardware!"](https://www.youtube.com/watch?v=BP6NxVxDQIs)
  - [CppCon 2015: Chandler Carruth "Tuning C++: Benchmarks, and CPUs, and Compilers! Oh My!"](https://www.youtube.com/watch?v=nXaxk27zwlk&feature=youtu.be)
- Catching pandas performance regressions using snakeviz (~flamegraph) and a line profiler
  - [Maintaing Performance by Tom Augspurger](https://tomaugspurger.github.io/maintaing-performance.html)
- A user name length can change performance (and other random perf bits). A super fun talk.
  - ["Performance Matters" by Emery Berger](https://www.youtube.com/watch?v=r-TLSBdHe1A&feature=share)
- [CppCon 2019: Chandler Carruth “There Are No Zero-cost Abstractions”](https://www.youtube.com/watch?v=rHIkrotSwcc&feature=share)
- This is a classic. [Why is GNU grep so fast?](https://lists.freebsd.org/pipermail/freebsd-current/2010-August/019310.html) It does very little work and it does this to as few bytes as possible. These advice apply to a much wider number of situations.
- Measure everything, things can be counter intuitive. Really cool simple demos on perf tracking. [GothamGo 2019 – "Slice Recycling Performance and Pitfalls" by David Golden](https://www.youtube.com/watch?v=x_qxkhK1Kgw&feature=share)

- Two topics here. First, various crazy optimisations compilers can do for you these days (e.g. detect you're implementing POPCNT), second, infrastructure behind the de-facto standard Godbolt tool (it's actually called Compiler Explorer, who knew?) - how it handles security, caching, deployment etc..
  - [CppCon 2017: Matt Godbolt “What Has My Compiler Done for Me Lately? Unbolting the Compiler's Lid”](https://www.youtube.com/watch?v=bSkpMdDe4g4&feature=youtu.be&t=2852)

- Assembly gets used in Go in places where performance is deemed more important than maintainability and other niceties. 
  - [Michael McLoughlin's Geohash in Golang Assembly](https://mmcloughlin.com/posts/geohash-assembly) goes in depth in this topic, describing in detail how and why to implement an assembly-powered implementation of a simple-ish algorithm.
  - [dotGo 2019 - Michael McLoughlin - Better x86 Assembly Generation with Go](https://www.youtube.com/watch?v=6Y5CZ7_tyA4&feature=share) - assembly is hard to get right, having higher level tools that allow you to generate it instead seems super helpful. You still need to know what you're doing, but you have fewer opportunities to shoot yourself in the foot.


### Languages

#### C/C++
I've only written tiny bits of C++ and I was quite surprised how it differs from the C/C++ code I saw years and years ago. And here's [Kate Gregory talking](https://www.youtube.com/watch?v=YnWhqhNdYyk&feature=share) about how modern C++ should be taught as exactly that, modern C++.

#### Python

Python wheels are still magic to me, but they are a tiny bit less magic now, [thanks to this PyCon talk](https://www.youtube.com/watch?v=02aAZ8u3wEQ&feature=share).

There's a walrus operator coming in Python 3.8. Do you not know? [Here's not only what it is](https://www.youtube.com/watch?v=6uAvHOKofws&feature=share), but also a reminder that we should be nice to other people on the internet, and what's changing in terms of Python governance.


I teach Python and I often struggle when explaining decorators, [this talk](https://www.youtube.com/watch?v=MjHpMCIvwsY&feature=share) is a great overview of not just what they are, but also *why* they work.

[A well paced talk](https://www.youtube.com/watch?v=-WDV0-OB4fE&feature=share) on setup.py and PyPI.

I knew that CPython can efficiently concatenate strings, despite their immutability. I never knew why, thanks for this explanation. https://blog.ganssle.io/articles/2019/11/string-concat.html

Raymond Hettinger is a core Python developer, he's quite known for being a great speaker and educator. Here's [a talk on Python dictionaries](https://www.youtube.com/watch?v=p33CVV29OG8), how they came up to be, how their implementation changed over the years and what it means for their users.

Raise your hand if you only use IPython for syntax highlighting, easier help dialog, and multiline support. Turns out [it has a lot more features](https://youtu.be/3i6db5zX3Rw).

Mypy [has generics and interfaces](https://www.youtube.com/watch?v=UQo-ebJk4a4).

#### Go

It’s a bit annoying that Go can’t mock, so you have to do all this [interface kungfu](https://www.youtube.com/watch?v=_NKQX-TdNMc&feature=share). But at least it’s more explicit.

A very nice and clear explanation of [how maps are implemented in Go](https://dave.cheney.net/2018/05/29/how-the-go-runtime-implements-maps-efficiently-without-generics).

A frustrating thing about inlining in Go is that there's a fairly arbitrary cost model and you sometimes end up fighting it (lookup George Tankersley's talks on YouTube). There have been tons of discussions about whether or not it should be user configurable, if inlining hints should happen at the call sites or function definitions etc. It's quite a nice discussion that helps people understand the toolchain. It also goes to show that while a self hosted build system is nice, you forgo decades of gcc/llvm optimisations. https://github.com/golang/go/issues/17566

#### JavaScript

- A great talk by the creator of Node.js. [What he regrets and what he’d do differently.](https://youtu.be/M3BM9TB-8yA)

#### WebAssembly

I've been following the developments of WebAssembly a bit over the past few years, but I haven't seen such a convincing and clear explanation as to why it's a big deal. This is a great presentation in terms of clarity, content, and form. Thanks, @callahad. https://www.youtube.com/watch?v=TGo3vJVTlyQ
