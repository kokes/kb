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

### Internals

#### Architecture

I love to listen to data architecture descriptions and I love it ever more when the bottom line is: we just use Postgres (usually heavily partitioned). There are a few podcast episodes on these, there's [Outlier](https://softwareengineeringdaily.com/2018/06/29/data-engineering-automation-with-mike-kim/), [Pex](https://softwareengineeringdaily.com/2018/06/22/video-search-with-rasty-turek/) or [Heap](https://www.dataengineeringpodcast.com/heap-with-dan-robinson-episode-36/).


Firecracker - isolation is not just about Docker, because security and performance are two major areas of research in container isolation. Firecracker is an OSS offering from Amazon, which they already use in Lambda and the main ruse is that it allows for extremely low latency and low utilisation of resources. https://www.amazon.science/publications/firecracker-lightweight-virtualization-for-serverless-applications

A periodic reminder that [You are not Google](https://blog.bradfieldcs.com/you-are-not-google-84912cf44afb).


A nice overview of how Tailscale works. Reminds me of using Hamachi back in the day, worked like magic. https://tailscale.com/blog/how-tailscale-works/


The Amazon Builders’ Library is a nice resource, I hope they add more content over time. Here’s a bit of it [in video form](https://www.youtube.com/watch?v=sKRdemSirDM&feature=emb_logo) (I liked the shuffle sharding explanation). It has text form, but I only watched this.

It's not all just about velocity, features and such, it's also about good design. [Here's a Google talk](https://www.youtube.com/watch?v=bmSAYlu0NcY&feature=share) by John Ousterhout about that very topic. He also [has a new book about that](https://twitter.com/johnousterhout/status/989260683836506112?lang=en), it's decent but fairly high level.

“One of the main skills you need to have is evaluating new technology.” https://youtu.be/d5bNZX8tpiI

[PID loops at AWS](https://www.youtube.com/watch?v=3AxSwCC7I4s&feature=share) and other fun stuff. Never knew this whole area even existed.

#### Data structures

There are tons of interesting data structures and algorithms, Nicholas Ormrod covers a few of them in [this great CppCon talk](https://www.youtube.com/watch?v=YA-nB2wjVcI). I highly recommend the last part where he talks about [HyperLogLog](https://en.wikipedia.org/wiki/HyperLogLog), an algorithm which is very close to magic. Oh and I also gave a talk on HyperLogLog and similar algorithms [at PyData Amsterdam](https://www.youtube.com/watch?v=8Ean3Bx_o_M).

Being a big fan of Bloom filters, I really enjoyed this paper on Cuckoo filters. They are better in many ways, one only has to be careful about insertion performance at high occupancy. https://www.cs.cmu.edu/~dga/papers/cuckoo-conext2014.pdf

I dislike all things Java/JVM, but I'm always astonished at Elasticsearch's performance. [In this video](https://www.youtube.com/watch?v=eQ-rXP-D80U&feature=share), Adrien Grand describes at length what sort of data structures and algorithms are used in Elasticsearch and Lucene.

This short talk on CRDTs is not only good in terms of explaining the basics of conflict free data structures, but the speaker also highlights good UX in data applications, something that is grossly overlooked. https://www.youtube.com/watch?v=DEcwa68f-jY


Locks and how to avoid their performance penalties. [A great talk by Kavya Joshi](https://www.youtube.com/watch?v=tjpncm3xTTc).

#### Parallelism

This is a nice and concise overview of parallel computing primitives in Python. Be it processes, threads, workers or coroutines. https://youtu.be/0RaotdCa_j0

Raft - how does one achieve consensus across a distributed system? Where do we keep the truth and how do we handle failures? Paxos used to be the answer, but it's a notoriously hard problem and this implementation was quite difficult to work with. Raft is a newer and simpler solution to this coordination problem and it's widely used in distributed systems. https://raft.github.io/raft.pdf

Multiprocessing is scary, here are some great tips on how not to go crazy
https://www.youtube.com/watch?v=5dMOYf0b_20


#### software development

It's been a while since I needed gdb, but it's good to see I used maybe half a percent of its functionality. https://www.youtube.com/watch?v=PorfLSr3DDI&feature=share


Code reviews are essential, but that doesn't mean we have to do PEP8 and other code quality checks by hand. [Automate these away as much as possible.](https://www.youtube.com/watch?v=G1lDk_WKXvY)

Dependency management is hard. Here are [a few notes from the creator of pipenv](https://www.youtube.com/watch?v=GBQAKldqgZs). I'm still not entirely sold on pipenv, but it's a decent tool for the job.

We need to learn from mistakes we or others have made. Here's a post on reading postmortems. https://danluu.com/postmortem-lessons/


[Things I Learnt The Hard Way (in 30 Years of Software Development)](https://blog.juliobiason.net/thoughts/things-i-learnt-the-hard-way/)


[Crash early and crash often for more reliable software](https://medium.com/@mattklein123/crash-early-and-crash-often-for-more-reliable-software-597738dd21c5)

I expected a dry talk on code reviews and it ended up being [a really nice overview of culture, soft skills, helping newcomers, dealing with anxiety, GTD etc](https://youtu.be/iNG1a--SIlk).


Forget PEP8, version control, reviews or tests. No bash, subprocess run all the things, just good old sloppy code that *solves your problem*. [Super fast and excellent](https://www.youtube.com/watch?v=Jd8ulMb6_ls).


TDD has become almost a religion. Here's a great talk on [where it all went wrong](https://www.youtube.com/watch?v=EZ05e7EMOLM). Ian Cooper covers the origins - like red-green-refactor - but also the bad practices we've come to adopt, the most prominent one being that we tend to test implementations rather than behaviour. Once you factor in your implementation details into your test, you've deviated from the original idea of TDD.


I can highly recommend all of Kyle Kingsbury's talks. He built this testing suite, Jepsen, which verifies data stores and checks them for consistency guarantees, data loss, split brain, dirty reads, ... Oh and [this talk](https://www.youtube.com/watch?v=tRc0O9VgzB0) includes zings like “Turns out the write ahead log wasn’t write ahead.” If you're not fluent in this terminology, I can highly recommend [Martin Kleppmann's book](http://dataintensive.net/).


[Writing system software: code comments](http://antirez.com/news/124)

[The Skills Poor Programmers Lack](https://justinmeiners.github.io/the-skills-programmers-lack/)


### Legacy software

With Python 2 ~~about to be~~ deprecated, there are a few talks about migration to Python 3. There's Facebook's take [from PyCon 2018](https://youtu.be/H4SS9yVWJYA) and Instagram's [from PyCon 2017](https://www.youtube.com/watch?v=66XoCk79kjM). Oh and the most recent now - how [Pinterest did the same](https://www.youtube.com/watch?v=e1vqfBEAkNA&feature=share) - it's a bit more about the code differences rather than how they actually migrated.


Our journey to type checking 4 million lines of Python https://blogs.dropbox.com/tech/2019/09/our-journey-to-type-checking-4-million-lines-of-python/

Rewriting software always leads to broken deadlines, new bugs everywhere, reinventing the wheels etc. I've done this a few times and it was always the same. Here's [a good overview of how a lot larger rewrites turned out](https://medium.com/@herbcaudill/lessons-from-6-software-rewrite-stories-635e4c8f7c22).


Lessons learned from rewriting code in my 10+ years as a developer http://huseyinpolatyuruk.com/2019/02/04/lessons-learned-from-rewriting-code-in-my-10-years-as-a-developer/

Legacy code is a pain in the ass, but I somehow like it. This is a great overview of tips and tricks https://www.youtube.com/watch?v=YsMUlNGF1no
