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
