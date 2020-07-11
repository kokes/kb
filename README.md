## development

### perf

- Instructions can be essentially free [if you're waiting for your memory to catch up](https://www.youtube.com/watch?v=jEG4Qyo_4Bc&feature=share). Here's [a bit of a deep dive](https://www.youtube.com/watch?v=BP6NxVxDQIs) from a past CppCon. And [here's how you measure it](https://www.youtube.com/watch?v=nXaxk27zwlk&feature=youtu.be), by Chandler Carruth, one of my favourite speakers.


https://twitter.com/pndrej/status/1247620953900748802?s=12

------------------------

https://www.youtube.com/watch?v=r-TLSBdHe1A&feature=share

A super fun talk about performance trickiness from an angle I havent known about. Like... user name can change performance. 

------------------------

------------------------

https://www.youtube.com/watch?v=rHIkrotSwcc&feature=share

There are no zero cost abstractions

------------------------


- This is a classic. [Why is GNU grep so fast?](https://lists.freebsd.org/pipermail/freebsd-current/2010-August/019310.html) It does very little and it does this to as few bytes as possible. These advice apply to a much wider number of situations.



------------------------

https://www.youtube.com/watch?v=x_qxkhK1Kgw&feature=share

Measure everything. Really cool simple demos on perf tracking. 

------------------------

george tank youtube talks

- Matt Godbolt is another of my favourite speakers, here's [a talk mostly about compilers](https://youtu.be/bSkpMdDe4g4?t=2852), but also about his super popular site, [Compiler Explorer](https://godbolt.org/), how it works, what resources it needs (it seems ridiculously efficient), how it does isolation, security etc.

------------------------

https://www.youtube.com/watch?v=jEG4Qyo_4Bc&feature=share

Instructions can be free if youre waiting for memory

https://www.youtube.com/watch?v=BP6NxVxDQIs&list=WL&index=13&t=0s

https://youtu.be/nXaxk27zwlk - here is how to measure it

------------------------

------------------------

title: Geohash in Golang Assembly: Lessons in absurd optimization:

https://mmcloughlin.com/posts/geohash-assembly

------------------------

- Writing assembly is tough, I'd never go that road. But I've just found out that even people proficient in assembly use tooling that helps build it. There's a Python tool and a Go tool, [here's a good introduction](https://www.youtube.com/watch?v=6Y5CZ7_tyA4&feature=share). The speaker also has a fun post about [absurd optimisations](https://mmcloughlin.com/posts/geohash-assembly).

------------------------

title: simdjson

Dan @lemire's talk on the internals of simdjson from last year's QCon is finally on YouTube.

It's a well paced talk, I really liked the simd tricks for integer parsing and the nibble stuff for tokenisation.

https://www.youtube.com/watch?v=wlvKAT7SZIQ

it has a transcript https://www.infoq.com/presentations/simdjson-parser/

------------------------


### languages

#### rust

Rustaceans tend to be quite... enthusiastic, but this is a good, somber [overview of borrower and mutex primitives](https://youtu.be/s19G6n0UjsM).



------------------------

title: Initial reactions to Rust

Bryan Cantrill got me hooked (link?)
  He r commends learning the language, not writing code, might be a food idea

Better std::collections
i128
generics (they require tooling for quality intellisense, vs code is failing me)
better optimisation (llvm)
similarly bad ecosystem as go
generally better performant libraries (csv)
interesting error handling
better than go: iterators <3 hashsets <3

march native

the compiler is very helpful in telling you what you did wrong (of which you'll do a lot)
it moves way too fast for my liking - much faster than go

the docs are quite elaborate, but also confusing (e.g. the function signatures)

hashmap.entry(line.clone()).or_insert(1);
   SOO NICE, just like python

accumulators etc.

mutable strings - in go I have zero control over allocations when creating 

strings (they are omitted in some map accesses though)

Incl str!!!

BUUUUT, it's super complex and moves fast

------------------------

------------------------

title: Falling in love with Rust

http://dtrace.org/blogs/bmc/2018/09/18/falling-in-love-with-rust/

------------------------


------------------------

https://www.youtube.com/watch?v=2ajos-0OWts&feature=share

Interesting design dexision in Rust, not just from a language theory perspective, but more about user usage. Also talks about language governance and its evolution. 

------------------------

Bryan Cantrill tends to get excited about stuff. Here he [talks about various languages](https://youtu.be/HgtRAbE1nBM) and why he likes Rust. Oh and [here as well](https://www.youtube.com/watch?v=2wZ1pCpJUIM). I also enjoyed his talk on [growing teams](https://www.youtube.com/watch?v=1KeYzjILqDo).

Rustaceans tend to be quite... enthusiastic, but this is a good, somber [overview of borrower and mutex primitives](https://youtu.be/s19G6n0UjsM).

https://www.youtube.com/watch?v=A3AdN7U24iU&feature=share

How rust is future proof and compatible to be usable in fourty years. And also why you should move from C. 

------------------------

Weld compiler in Rust

why rust?
what does it do? is it like XLA?

looks cool

https://www.youtube.com/watch?v=gr11KYrB78E

------------------------

------------------------

title: Deploying new features in a *language* takes tiiiime

https://www.youtube.com/watch?v=lJ3NC-R3gSI

------------------------

#### C/C++
I've only written tiny bits of C++ and I was quite surprised how it differs from the C/C++ code I saw years and years ago. And here's [Kate Gregory talking](https://www.youtube.com/watch?v=YnWhqhNdYyk&feature=share) about how modern C++ should be taught as exactly that, modern C++.


------------------------

https://www.youtube.com/watch?v=iz5Qx18H6lg&feature=share

C++ has come a looong way. But also means its difficykt af

------------------------

#### Python


Python wheels are still magic to me, but they are a tiny bit less magic now, [thanks to this PyCon talk](https://www.youtube.com/watch?v=02aAZ8u3wEQ&feature=share).


There's a walrus operator coming in Python 3.8. Do you not know? [Here's not only what it is](https://www.youtube.com/watch?v=6uAvHOKofws&feature=share), but also a reminder that we should be nice to other people on the internet, and what's changing in terms of Python governance.



I teach Python and I often struggle when explaining decorators, [this talk](https://www.youtube.com/watch?v=MjHpMCIvwsY&feature=share) is a great overview of not just what they are, but also *why* they work.




------------------------

https://www.youtube.com/watch?v=-WDV0-OB4fE&feature=share

Well paced explanation of setup.py and pypi

------------------------


------------------------

https://www.youtube.com/watch?v=02aAZ8u3wEQ&feature=share

Wheels are still magic, but less so

------------------------

------------------------

‪I knew that CPython can efficiently concatenate strings, despite their immutability. I never knew why, thanks for this explanation. https://blog.ganssle.io/articles/2019/11/string-concat.html‬

------------------------


- Raymond Hettinger is a core Python developer, he's quite known for being a great speaker and educator. Here's [a talk on Python dictionaries](https://www.youtube.com/watch?v=p33CVV29OG8), how they came up to be, how their implementation changed over the years and what it means for their users.




title: We learned this the hard way

https://hakibenita.com/fast-load-data-python-postgresql

------------------------

------------------------

title: Ipython has a crapton of features

https://youtu.be/3i6db5zX3Rw

------------------------

------------------------

https://www.youtube.com/watch?v=UQo-ebJk4a4

Wait, mypy has generics and interfaces??

------------------------

------------------------

https://www.youtube.com/watch?v=e1vqfBEAkNA&feature=share

Many difference between py2 and 3s, not really how they migrated :(

------------------------

#### Go

------------------------

https://www.youtube.com/watch?v=_NKQX-TdNMc&feature=share

It’s a bit annoying that Go can’t mock, so you have to do all this interface kungfu. But at least it’s more explicit. 

------------------------

A very nice and clear explanation of [how maps are implemented in Go](https://dave.cheney.net/2018/05/29/how-the-go-runtime-implements-maps-efficiently-without-generics).


------------------------


https://www.youtube.com/watch?v=kNHo788oO5Y&feature=share

------------------------

title: go inlining

comment for: https://lemire.me/blog/2020/06/04/the-go-compiler-needs-to-be-smarter/

A frustrating thing about inlining in Go is that there's a fairly arbitrary cost model and you sometimes end up fighting it (lookup George Tankersley's talks on YouTube). There have been tons of discussions about whether or not it should be user configurable, if inlining hints should happen at the call sites or function definitions etc.
It's quite a nice discussion that helps people understand the toolchain. It also goes to show that while a self hosted build system is nice, you forgo decades of gcc/llvm optimisations. https://github.com/golang/go/issues/17566

------------------------

#### javascript

- A great talk by the creator of Node.js. [What he regrets and what he’d do differently.](https://youtu.be/M3BM9TB-8yA)


#### webassembly

https://www.youtube.com/watch?v=UtjoaTfbdcA&feature=share

------------------------

title: webassembly beyond the web

I've been following the developments of WebAssembly a bit over the past few years, but I haven't seen such a convincing and clear explanation as to why it's a big deal. This is a great presentation in terms of clarity, content, and form. Thanks, @callahad. https://www.youtube.com/watch?v=TGo3vJVTlyQ

------------------------

### internals

#### algorithms

------------------------

https://www.youtube.com/watch?v=9zpHdh70Xdk&feature=share

Averaging is not as easy as i thought

------------------------


4. MapReduce - one of the most influential data engineering papers in the past two decades - it directly lead to data processing in Hadoop and later to Spark, both of which leverage these ideas of horizonally scaling computation on a bunch of nodes in a fault tolerant way. https://static.googleusercontent.com/media/research.google.com/en//archive/mapreduce-osdi04.pdf


#### architecture

- I love to listen to data architecture descriptions and I love it ever more when the bottom line is: we just use Postgres (usually heavily partitioned). There are a few podcast episodes on these, there's [Outlier](https://softwareengineeringdaily.com/2018/06/29/data-engineering-automation-with-mike-kim/), [Pex](https://softwareengineeringdaily.com/2018/06/22/video-search-with-rasty-turek/) or [Heap](https://www.dataengineeringpodcast.com/heap-with-dan-robinson-episode-36/).


1. Firecracker - isolation is not just about Docker, because security and performance are two major areas of research in container isolation. Firecracker is an OSS offering from Amazon, which they already use in Lambda and the main ruse is that it allows for extremely low latency and low utilisation of resources. https://www.amazon.science/publications/firecracker-lightweight-virtualization-for-serverless-applications


------------------------

title: You Are Not Google

https://blog.bradfieldcs.com/you-are-not-google-84912cf44afb

------------------------


A nice overview of how Tailscale works. Reminds me of using Hamachi back in the day, worked like magic.

https://tailscale.com/blog/how-tailscale-works/

-----

The Amazon Builders’ Library is a nice resource, I hope they add more content over time. Here’s a bit of it in video form (I liked the shuffle sharding explanation).

It has text form, but I only watched this.

https://www.youtube.com/watch?v=sKRdemSirDM&feature=emb_logo

---

It's not all just about velocity, features and such, it's also about good design. [Here's a Google talk](https://www.youtube.com/watch?v=bmSAYlu0NcY&feature=share) by John Ousterhout about that very topic. He also [has a new book about that](https://twitter.com/johnousterhout/status/989260683836506112?lang=en), it's on my todo list.


------------------------

title: Thinking architectually

“One of the main skills you need to have is evaluating new technology.”

Theres a book as well

https://youtu.be/d5bNZX8tpiI

------------------------


------------------------

https://www.youtube.com/watch?v=IZ8CBwP5nlA&feature=share

Just use fewer texhnologies. Dont use complex contraptions

------------------------

https://www.youtube.com/watch?v=3AxSwCC7I4s&feature=share

Never knew this whole area even existed as a thing


#### data structures

- There are tons of interesting data structures and algorithms, Nicholas Ormrod covers a few of them in [this great CppCon talk](https://www.youtube.com/watch?v=YA-nB2wjVcI). I highly recommend the last part where he talks about [HyperLogLog](https://en.wikipedia.org/wiki/HyperLogLog), an algorithm which is very close to magic. Oh and I also gave a talk on HyperLogLog and similar algorithms at [this year's PyData Amsterdam](https://www.youtube.com/watch?v=8Ean3Bx_o_M).


------------------------

https://www.youtube.com/watch?v=eQ-rXP-D80U&feature=share




------------------------


A very nice and clear explanation of [how maps are implemented in Go](https://dave.cheney.net/2018/05/29/how-the-go-runtime-implements-maps-efficiently-without-generics).

------------------------


------------------------

title: Cuckoo

‪Being a big fan of Bloom filters, I really enjoyed this paper on Cuckoo filters. They are better in many ways, one only has to be careful about insertion performance at high occupancy. https://www.cs.cmu.edu/~dga/papers/cuckoo-conext2014.pdf‬

------------------------

- I dislike all things Java/JVM, but I'm always astonished at Elasticsearch's performance. [In this video](https://www.youtube.com/watch?v=eQ-rXP-D80U&feature=share), Adrien Grand describes at length what sort of data structures and algorithms are used in Elasticsearch and Lucene.


title: CRDT

This short talk on CRDTs is not only good in terms of explaining the basics of conflict free data structures, but the speaker also highlights good UX in data applications, something that is grossly overlooked. https://www.youtube.com/watch?v=DEcwa68f-jY

------------------------

------------------------

title: How locks work

And how to avoid their performance penalties. A great talk by Kavya.

https://www.youtube.com/watch?v=tjpncm3xTTc

------------------------

#### time

- UTC, just use UTC. [Turns out, it's not quite a universal advice as it might seem.](https://codeblog.jonskeet.uk/2019/03/27/storing-utc-is-not-a-silver-bullet/)


------------------------

title: Keeping time in distributed systems

"Time is hard, man"

Didn't know much about Google's TrueTime

https://www.youtube.com/watch?v=BRvj8PykSc4

------------------------

------------------------

‪A Miroslav Šedivý pěkně popsal IANA a poukázal na hezký outliery - já znal jen Istanbul, takže jsem zas o trochu chytřejší. https://youtu.be/mHaz5laPyHE‬

------------------------

#### parallelism

------------------------

Lots of parallel primitives in Python, this is a great oberview https://youtu.be/0RaotdCa_j0

------------------------

5. Raft - how does one achieve consensus across a distributed system? Where do we keep the truth and how do we handle failures? Paxos used to be the answer, but it's a notoriously hard problem and this implementation was quite difficult to work with. Raft is a newer and simpler solution to this coordination problem and it's widely used in distributed systems. https://raft.github.io/raft.pdf

------------------------

title: multiprocessing is scary

here are some great tips on how not to go crazy
https://www.youtube.com/watch?v=5dMOYf0b_20

------------------------

This is a nice and concise overview of parallel computing primitives in Python. Be it processes, threads, workers or coroutines. https://youtu.be/0RaotdCa_j0

------------------------

#### type checking

------------------------

title: Our journey to type checking 4 million lines of Python

https://blogs.dropbox.com/tech/2019/09/our-journey-to-type-checking-4-million-lines-of-python/

Quite a large scale thing

------------------------

------------------------

title: mypy is pretty good

its pretty painful compared to properly typed langugages, but it's better than nothing

http://calpaterson.com/mypy-hints.html

------------------------

#### software development

------------------------

https://www.youtube.com/watch?v=PorfLSr3DDI&feature=share

------------------------


- Code reviews are essential, but that doesn't mean we have to do PEP8 and other code quality checks by hand. [Automate these away as much as possible.](https://www.youtube.com/watch?v=G1lDk_WKXvY)
- Dependency management is hard. Here are [a few notes from the creator of pipenv](https://www.youtube.com/watch?v=GBQAKldqgZs). I'm still not entirely sold on pipenv, but I do tend to use it, because it's nicely built into our deployment flow.


------------------------

title: Reading postmortems

https://danluu.com/postmortem-lessons/

------------------------

------------------------

title: Things I Learnt The Hard Way (in 30 Years of Software Development)

https://blog.juliobiason.net/thoughts/things-i-learnt-the-hard-way/

Dear new devs

------------------------

------------------------

title: Crash early and crash often for more reliable software

https://medium.com/@mattklein123/crash-early-and-crash-often-for-more-reliable-software-597738dd21c5

Sont do try except pass

------------------------

- I expected a dry talk on code reviews and it ended up being [a really nice overview of culture, soft skills, helping newcomers, dealing with anxiety, GTD etc](https://youtu.be/iNG1a--SIlk).
- Forget PEP8, version control, reviews or tests. No bash, subprocess run all the things, just good old sloppy code that *solves your problem*. [Super fast and excellent](https://www.youtube.com/watch?v=Jd8ulMb6_ls).


https://www.youtube.com/watch?v=MYucYon2-lk&feature=share

------------------------

title: TDD where did it go wrong

- TDD has become almost a religion. Here's a great talk on [where it all went wrong](https://www.youtube.com/watch?v=EZ05e7EMOLM). Ian Cooper covers the origins - like red-green-refactor - but also the bad practices we've come to adopt, the most prominent one being that we tend to test implementations rather than behaviour. Once you factor in your implementation details into your test, you've deviated from the original idea of TDD.

------------------------


- I can highly recommend all of Kyle Kingsbury's talks. He built this testing suite, Jepsen, which verifies data stores and checks them for consistency guarantees, data loss, split brain, dirty reads, ... Oh and [this talk](https://www.youtube.com/watch?v=tRc0O9VgzB0) includes zings like “Turns out the write ahead log wasn’t write ahead.” If you're not fluent in this terminology, I can highly recommend [Martin Kleppmann's book](http://dataintensive.net/).


------------------------

title: Writing system software: code comments. - <antirez>

http://antirez.com/news/124

------------------------

------------------------

title: The Skills Poor Programmers Lack

https://justinmeiners.github.io/the-skills-programmers-lack/

------------------------


### data

#### architecture, engineering


------------------------

title: kafka zookeeper

I've been looking forward to Kafka dropping Zookeeper and always viewed the change as just swapping a part. Turns out there are good reasons other than simplifying deployment. This is a good talk on that. https://www.youtube.com/watch?v=3qNNinbnWmw

------------------------

2. Millions of tiny databases - Amazon runs exabytes of storage for their customers and it turns out that running replicated storage reliably is quite hard and it calls for unorthodox solutions. https://assets.amazon.science/c4/11/de2606884b63bf4d95190a3c2390/millions-of-tiny-databases.pdf
------------------------


------------------------

title: Transparent Hierarchical Storage Management with Apache Kudu and Impala

https://blog.cloudera.com/blog/2019/03/transparent-hierarchical-storage-management-with-apache-kudu-and-impala/

------------------------

------------------------

title: ongoing by Tim Bray · On Sharding

https://www.tbray.org/ongoing/When/201x/2019/09/25/On-Sharding

Sharding is hard

------------------------

------------------------

https://www.youtube.com/watch?v=BuE6JvQE_CY&feature=share

Luckily the answer is not quite. 

law of headlines

------------------------


------------------------

title: map reduce paper

the map reduce paper is super easy to read and there are tons of things I like about it
- it's driven by a real need (compute a lot of stuff)
- it uses commodity hardware, which later enabled thousands of developers worldwide to leverage the methodology
- they describe a system of backup tasks that fix the issue of outliers taking ages to complete
- they focus on the fact that the system allows for a much simplified computing model - people without the knowledge of distributed computing can write massively paralelised workloads - in a way it's similar to SQL

https://static.googleusercontent.com/media/research.google.com/en//archive/mapreduce-osdi04.pdf

------------------------

------------------------

Networks are problematic. Ever since reading Designing Data Intensive Applications, I’ve been more aware of this. This article, co-authored by Kyle Kingsbury of Jepsen, describes a whole host of network issues. https://dl.acm.org/doi/10.1145/2639988.2655736

------------------------


3. Kafka - message queues have a looong tradition in computer science, but they are usually thought of as ephemeral - messages come, get processed and get discarded. Kafka was the first major system where storing messages and replays were accounted for in its design. It created a whole new area of data processing, where the stream plays a more important role than storage (=database), because you can always recreate the latter from the former, but not vice versa. http://notes.stephenholiday.com/Kafka.pdf



------------------------

https://www.youtube.com/watch?v=1spKXX2W7Eo&feature=share

Batch is operationally simpler than streaming. 

Windowing is hard. 

Stream to stream joins are hard. 

The value in big data is democratization, not size or ML. 

------------------------


title: Delivering billions of messages exactly once

https://segment.com/blog/exactly-once-delivery/

------------------------

title: Is Hadoop Dead?

https://tech.marksblogg.com/is-hadoop-dead.html

------------------------

title: Metadata management in big data is a bitch

Here's an open source offering from the We company. I feel like this space is underserved by quality software. The "standard" of Apache Atlas is super heavyweight, I'm not willing to have Kafka or HBase to store a few rows of data, no way.

https://www.youtube.com/watch?v=dRaRKob-lRQ

------------------------


------------------------

title: Common Data Engineering Mistakes

New technology is not the key to success

Distributed processing is difficult

Engineering for imaginary scale problems

https://www.youtube.com/watch?v=mv7PLnwzLpM


----

read-level deduplication, cool arch

https://engineering.mixpanel.com/2019/07/18/petabyte-scale-data-deduplication/

#### dataframes

------------------------

https://www.youtube.com/watch?v=HVLPJnvInzM&feature=share

Plumbing is important. Plumbing is difficult. 

------------------------


------------------------

title: Careful about pandas

https://www.youtube.com/watch?list=PLGVZCDnMOq0oqs6RTJk4zZde86DZrgnzm&v=_-gJtO0XR48

------------------------

------------------------

https://www.youtube.com/watch?v=2Tt0i823-ec&feature=share

A super impressive live demo

------------------------


- One of the most cited issues with pandas has been its inability to contain integer series with nulls. This lack of support is caused by the treatment of nulls in series - pandas uses sentinel values rather than a separate bitarray. Here is [a good overview of what's changed recently](https://www.youtube.com/watch?v=gxvTVxlvH9w) by Jeff Reback, pandas' long time maintainer.

------------------------

title: pandas pipelines

Ondrej Kokes:palm_tree: 4:51 PM
It’s really painful to be working with Jupyter notebooks with hundreds of cells. Here’s a really really nice overview of pandas+Jupyter pipelines that allow you to create reproducible and easy to maintain pipelines with logging, all for the sake of maintainability. https://www.youtube.com/watch?v=yXGCKqo5cEY

Ondrej Kokes:palm_tree:  13 minutes ago
Much of the content is taken from these Modern Pandas tutorials, I can highly recommend them as supplementary reading. https://tomaugspurger.github.io/modern-1-intro.html

tomaugspurger.github.io
datas-frame – Modern Pandas (Part 1)
Posts and writings by Tom Augspurger

Ondrej Kokes:palm_tree:  12 minutes ago
And if you don’t want to watch the talk nor read the posts, just checkout the Contextual Help feature (time 4:30 in the video). It’s a super useful addition to your Jupyter Lab flow.

------------------------

#### spark

- If you working with Spark, chances are you've read something from Jacek Laskowski, he maintains [a few sites on the internals of Spark or Kafka](https://github.com/jaceklaskowski), these are really good resources relating to underdocumented pieces of code. One fairly recent addition to Spark is bucketing and Jacek [had a nice Spark Summit talk](https://www.youtube.com/watch?v=dv7IIYuQOXI) on the topic.



------------------------

title: Initial thoughts on Spark

scales better than pandas, that's great
api changes dramatically and fast - hard to adapt
learning scala is painful - seems like learning lua for torch - luckily PySpark is very good and outside rdd, the performance is great
lazy evaluation is fine, but it's hard to debug
locally, it's much slower
predicate pushdown is fantastic, but drill has that too
stack traces by default? I want normal logging
single-node setup is a breeze, unlike presto and other big data solutions
 too many ways you can do stuff - select a dataframe column in eight different ways

------------------------

spark cannot write to s3 in v4 only regions
    also, it cannot use aws by default

                .config('fs.s3a.endpoint', 's3.eu-central-1.amazonaws.com')
spark-submit --packages org.apache.hadoop:hadoop-aws:2.7.4 --conf spark.{driver,executor}.extraJavaOptions='-Dcom.amazonaws.services.s3.enableV4' pipeline.py
    note that this is only for hadoop2 (default on pypi)

    https://kokes.github.io/blog/2020/06/22/apache-spark-pyspark-s3.html

#### databases

------------------------

title: pg 13

Interesting things coming to postgres 12, further partitioning improvements, better JSON support, but mainly some internal changes that allow for pluggable storage, which is likely to be user-facing in pg13 https://www.youtube.com/watch?v=VMLl-t4H_KI

------------------------

I’m a sucker for database internals talks. Here’s a very clear talk about InfluxDB - memory layout, on disk serialisation, compression, hashing.

https://www.youtube.com/watch?v=rtEalnKT25I&feature=emb_logo


------------------------

------------------------

title: Postgres is great

And I did learn something - RETURNING within a CTE looks cool.

I'd recommend everyone to use window functions and generate_series though.

https://www.youtube.com/watch?v=HWfxUvW1ejw

------------------------

https://remusao.github.io/posts/2017-10-21-few-tips-sqlite-perf.html

------------------------

title: dynamo paper

The legendary Dynamo paper turns out to be a very dense piece of writing. Took me quite a while to parse it all, let alone understand at least some of it. https://allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf

There are a number of techniques they employ. I like the symmetric nodes thing, which allows for simpler scaling. Also, partitioning based on consistent hashing results in less network traffic when clusters resize.

Tunable performance, availability and durability is a great thing that I'd welcome elsewhere - when I know I don't need consistency or integrity, let me write loads quickly, please. Kafka works sort of similar, since you can tune replication properties to change performance.

I always thought the client library was just issuing API calls, but it turns out that in Dynamo, they not only do some conflict resolution, but also pull cluster topology to avoid relying on a load balancer, which leads to better latency.

Last but not least - Dynamo is not just about DynamoDB, but about a set of principles to build distributed key-value stores. So it applies more broadly.

Overall it's a good read, but it is fairly technical.

------------------------



------------------------

title: useful reminder

https://blog.jooq.org/2019/04/09/the-difference-between-sqls-join-on-clause-and-the-where-clause/

------------------------


https://www.youtube.com/watch?v=VMLl-t4H_KI&feature=share

----

- Postgres is my goto database and even after more than 20 years of development, there are new features introduced every year. The latest version, 11, is mostly focused around better partitioning and parallelisation. I liked two videos on it - Magnus Hagander [mostly focuses on features](https://www.youtube.com/watch?v=lgzXuFQ0Pbk), while Joe Conway [covers how development is done as well](https://www.youtube.com/watch?v=kPhs-wdrb58).


https://www.youtube.com/watch?v=JWQVDKw1HVk&feature=share


SQL statements don’t start with a select. Seems kinda obvious in retrospect, super clear and informative in any case.
SQL queries don't start with SELECT
Okay, obviously many SQL queries do start with SELECT (and actually this post is only about SELECT queries, not INSERTs or anything). But! Yesterday I was working on an explanation of window functi...
jvns.ca

------------------------

title: Taking DuckDB for a spin

https://uwekorn.com/2019/10/19/taking-duckdb-for-a-spin.html

------------------------

1. Dynamo paper - one that defined a hugely scalable key-value store, it talks about the topology of the system, how it achieves its level of consistency, scale etc. http://courses.cse.tamu.edu/caverlee/csce438/readings/dynamo-paper.pdf
2. Bigtable - one of the first "NewSQL" systems - hugely scalable relational systems, usually of denormalised tables and using SQL. Since horizontal scale has been a long-standing issue with classical RDBMS, these NewSQL systems try to forgo some of the guarantees of RDBMS (e.g. foreign keys or transaction), but offer much better scale. https://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf


6. Spanner - this scalable database by Google has one specific feature - it not only scales, but it does so while not sacrificing as much as Bigtable - it allows for transactions and other synchronisation principles, which are hard to implement in a distributed system. It does so using special kinds of clocks to keep time across geographies (it even uses GPS and other hardware help). It's amazing how you can keep track of time in these hugely unreliable systems and I can recommend one more talk on this topic (by Kavya Joshi, just search on youtube for her name + "clocks"). https://static.googleusercontent.com/media/research.google.com/en//archive/spanner-osdi2012.pdf

------------------------

title: modern sql

It's all about the ethos - SQL is not about CRUD, it's about fairly advanced things.

Markus Winand and his "you don't know SQL" presentation I always enjoy. He starts off with quite basic things, but always runs into weird features I haven't heard about.
More Than a Query Language: SQL in the 21st Century by Markus Winand
youtube.com
Ondrej Kokes
https://www.youtube.com/watch?v=MnEDHFOqqno
·
1s
Like system versioning - I do it using triggers since Postgres doesn't support it natively, but it turns out, Postgres might be getting it soon! https://commitfest.postgresql.org/25/2316/

------------------------

------------------------

title: postgres talks

Some rather good Postgres talks - more about data management than querying

indexing - what's out there apart from btree - https://www.youtube.com/watch?v=Xv0NFozBIbM

jsonb, its usage and indexing - https://www.youtube.com/watch?v=p9RItyeKbLQ

------------------------

------------------------

title: BigQuery ML

A very good overview of how ML tools can be implemented in a massively scalable engine like BigQuery. https://www.youtube.com/watch?v=svQdwU3iPp8

------------------------

------------------------

title: Advanced SQL - window frames – Michał Konarski

https://mjk.space/advances-sql-window-frames/

------------------------

When we talk about testing, I usually think of unit tests, maybe some basic integration testing. FoundationDB's Will Wilson talks about [deterministic testing](https://www.youtube.com/watch?v=4fFDFbi3toc&feature=youtu.be) and it's quite an astonishing display of effort one needs to go through to thoroughly and reliably test a complex distributed system like FoundationDB. Oh and they don't stop at software!

DynamoDB is amongst the better known NoSQL offerings, but being proprietary, we don't usually get to find out a lot about their architecture. Here, apart from [the Dynamo paper](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf), there's a nice architectural overview [from last year's AWS re:Invent](https://www.youtube.com/watch?v=yvBR71D0nAQ&feature=share).

title: Pg automatic indexes

One of my favourite things about postgres is the amount of tooling it provides (first or third party). My all time favourite is pg_stat_statements, but this one is really cool as well: index recommendation.

https://www.percona.com/blog/2019/07/22/automatic-index-recommendations-in-postgresql-using-pg_qualstats-and-hypopg/

------------------------

title: snowflake paper

A nice paper on the architecture and evolution of Snowflake, a popular modern data warehousing solution using tiered storage, separating of compute and storage and other elastic parts.
Building an elastic query engine on disaggregated storage
Building an elastic query engine on disaggregated storage, Vuppalapati, NSDI’20 This paper describes the design decisions behind the Snowflake cloud-based data warehouse. As the saying goes, …
blog.acolyer.org
Ondrej Kokes
@pndrej
·
9s
I'm a big fan of tiered storage since, as the paper reiterates, blob storage is very cheap and extremely durable, it doesn't have the characteristics of a local disk, let alone memory, so they try to make use of each of the three for what they are meant to be used.
Ondrej Kokes
@pndrej
·
7s
There are tons more things in the paper, be it scaling up and down, caring about utilisation of various resources, how consistent hashing works in situations of changing the number of nodes etc. etc.
Ondrej Kokes
@pndrej
Last but not least - they use a big-ish dataset of query statistics from real world warehouses - and this dataset is published alongside the paper.

------------------------

------------------------

title: 8 Major Improvements in PostgreSQL 12

https://www.enterprisedb.com/blog/8-major-improvements-postgresql-12

Cant wait to use pg12 - my fav is not mentioned though - generated columns

------------------------

#### text processing

------------------------

title: Fuzzy search

‪Pretty cool to see major performance wins in text similarity algos. Useful for clustering, fuzzy joins etc. I really liked the letter bitmap stuff. https://youtu.be/s0YSKiFdj8Q‬

------------------------

#### machine learning

- I'm not a huge fan of overhyped parts of ML/AI, so I welcomed [this sober post](https://www.ben-evans.com/benedictevans/2018/06/22/ways-to-think-about-machine-learning-8nefy).

- Learned indexes sound a bit like magic. Instead of being explicitly set up like regular indexes, these are inferred from data and can perform better. But it's better explain by one of the authors, [Tim Kraska](https://www.youtube.com/watch?v=mkIHC7xMSRQ) or perhaps [by Robert Rodgers](https://www.youtube.com/watch?v=0q9mxMekBeE).

- You don't have to have fancy math across all your slides, I much prefer clear talks with good examples. [Robert Rodger's talk on text summarisation](https://www.youtube.com/watch?v=VZ5BEKVxy9k) is just that. I actually saw this one live, it was great.



### web dev


------------------------

title: Quic

‪HTTP/3 is coming, here’s what’s new. https://youtu.be/izk4nbuzPuU‬

------------------------

https://www.youtube.com/watch?v=1jD7dBsg_Nw&feature=share

Gone are the days where we’d tell the server about encoding, mime types and compression. There are tons of things you can convey these days. 

------------------------

------------------------

https://www.youtube.com/watch?v=AdNJ3fydeao&feature=share

Sonrefreshing to dump shadow dom

------------------------


------------------------

title: The Ethics of Web Performance

https://timkadlec.com/remembers/2019-01-09-the-ethics-of-performance/

------------------------

chrome extensions can block rendering quite a bit
    https://www.debugbear.com/blog/2020-chrome-extension-performance-report

------------------------

title: Cost of JS

https://www.youtube.com/watch?v=X9eRLElSW1c

Don't measure performance just on iPhones and Pixel phones.

Don't ship large bundles.

Prefetch React on the first screen, but don't block the main thread.

------------------------

## ops

### why


------------------------

https://www.youtube.com/watch?v=jiWRTuF4yXk&feature=share

Modern developers should know more than just code, they should know devops as well. Here’s a great breakdown of why devops as code and testing matter. 

------------------------

### deployment

------------------------

https://www.youtube.com/watch?v=KqTySYYhPUE&feature=share

There is lots of infrastructure needed for reproducible and safe builds in an OSS world. Here’s Go’s solution. 



------------------------

Compiler Explorer: Behind the Scenes - always a pleasure listening to Matt Godbolt's talks.

https://www.youtube.com/watch?v=kIoZDUd5DKw


------------------------


Matt Godbolt is another of my favourite speakers, here's [a talk mostly about compilers](https://youtu.be/bSkpMdDe4g4?t=2852), but also about his super popular site, [Compiler Explorer](https://godbolt.org/), how it works, what resources it needs (it seems ridiculously efficient), how it does isolation, security etc.

---


a nice overview of tf
    https://www.youtube.com/watch?v=h970ZBgKINg

------------------------

title: prototype poisoning

it's interesting how you can isolate code in javascript - eg limiting disk access
https://www.youtube.com/watch?v=hP00w4r4zhg

there is also a trascript https://www.infoq.com/presentations/npm-security-realms-ses/

------------------------

### service meesh

- Service meshes (if that's the correct plural) are all the rage these days. And here's a [nice talk](https://www.youtube.com/watch?v=55yi4MMVBi4) by the author of [Envoy](https://www.envoyproxy.io/), which is quickly becoming the goto service mesh out there (Google announced a hosted version recently). If you like podcasts, check out [this episode](https://softwareengineeringdaily.com/2018/12/19/linkerd-service-mesh-with-william-morgan/) of Software Engineering Daily, it's about Linkerd.

### system failures

------------------------

title: Reading post mortems

Dan luu github and article
Kubernetes failure stories github

------------------------

### containers

- Building containters from scratch. Like, from basically nothing. [It's very clear, well paced, instructive.](https://www.youtube.com/watch?v=8fi7uSYlOdc)


------------------------

title: Intro Guide to Dockerfile Best Practices

https://blog.docker.com/2019/07/intro-guide-to-dockerfile-best-practices/

------------------------

- “If you’re listening to this podcast and you’re not using containers and you feel bad about it... please don’t.” Another great episode one realises that you don't have to be at the cutting edge of technology to function just fine. https://hanselminutes.com/645/container-catharsis-with-laura-frank-tacho

### cloud, vms and such

I define 1 DOD as the computational power of one $5/mo @digitalocean droplet, and I refuse to rely on any server technology that requires more than 1 DOD to be useful.

https://twitter.com/artemchistyakov/status/953435147034152960

## meta

### learning

title: Jak se vzdelavam

Datanews mail digesty
HN dvakrat denne
Pocket
Podcasty
Oreilly knihy
RSS

----

There is a great resource for technical insight, one that is more in depth than most blog posts, but shorter than books - technical papers! These can be in an academic setting, proceedings for a conference, or purely just a business sharing their insight about a given topic.

You can find thousands of papers on various topics, I tried to distill a short list of papers most relevant to some of the work we do. Some of these are real classics, some are a bit more esoteric.


### oss
- A good talk [on the basics of open source contribution](https://www.youtube.com/watch?v=JhPC6_rO08s) - what to do, how to get that first pull request submitted etc. Paul Ganssle is the maintainer of [dateutil](https://dateutil.readthedocs.io/en/stable/) (its parser is superb) and [a contributor to CPython](https://mail.python.org/pipermail/python-committers/2019-February/006567.html).

------------------------

title: Redis OSS

Reflections on 10 years of open source developments. I recommend the blog as a whole, the author often describes his thought processes behind designs and implementations of various features. http://antirez.com/news/129

------------------------

### team work

------------------------

title: How to ask good questions - Julia Evans

https://jvns.ca/blog/good-questions/

This is pretty essential. 

------------------------

I usually like more down to earth speakers, but [Jesse Anderson's notes on big data teams](https://www.youtube.com/watch?v=VkeleGIUSM8) ring true more often than not. He talks a lot about composition of teams, where things can go wrong, how you need veterans, how whiteboards can save you months etc.

---

I don’t watch too many soft skill talks, perhaps I should. This was a really clear overview of dealing with managers. The speaker repeatedly recommended Camille Fournier’s book, which has been sitting on my shelf way too long.

https://www.youtube.com/watch?v=INr31JkHlT0&feature=emb_logo


### debugging

tmux synchronised panes
https://www.youtube.com/watch?v=BMn0nSpeITY&feature=emb_logo


### legacy software

- With Python 2 about to be deprecated, there are a few talks about migration to Python 3. There's Facebook's take [from PyCon 2018](https://youtu.be/H4SS9yVWJYA) and Instagram's [from PyCon 2017](https://www.youtube.com/watch?v=66XoCk79kjM). Oh and the most recent now - how [Pinterest did the same](https://www.youtube.com/watch?v=e1vqfBEAkNA&feature=share) - it's a bit more about the code differences rather than how they actually migrated.



------------------------

title: Lessons from 6 software rewrite stories

https://medium.com/@herbcaudill/lessons-from-6-software-rewrite-stories-635e4c8f7c22

------------------------

- Rewriting software always leads to broken deadlines, new bugs everywhere, reinventing the wheels etc. I've done this a few times and it was always the same. Here's [a good overview of how a lot larger rewrites turned out](https://medium.com/@herbcaudill/lessons-from-6-software-rewrite-stories-635e4c8f7c22).


------------------------

title: Lessons learned from rewriting code in my 10+ years as a developer – Huseyin Polat Yuruk

http://huseyinpolatyuruk.com/2019/02/04/lessons-learned-from-rewriting-code-in-my-10-years-as-a-developer/

Dear new devs - rewriting

------------------------

------------------------

title: Legacy code is a pain in the ass, but I somehow like it

This is a great overview of tips and tricks

https://www.youtube.com/watch?v=YsMUlNGF1no

------------------------


### public speaking

------------------------

title: best speakers

aphyr
brian cantrill
hoettinger
godbolt
ted malaska
chandler carruth

------------------------

"I can deploy while in warrior three."

https://www.youtube.com/watch?v=Mz3JeYfBTcY&feature=share


### biz

- Shortly after Microsoft announced its aquisition of Github, Gitlab's founder and CEO, Sid Sijbrandij, [went on The Architecht's Show](http://architechtshow.com/ep-60-gitlab-ceo-on-competing-with-microsoft-betting-on-kubernetes-and-learning-to-scale) to talk all things Gitlab and their competition.



## version control


------------------------

title: Write long commits

https://fatbusinessman.com/2019/my-favourite-git-commit
https://blog.mocoso.co.uk/talks/2015/01/12/telling-stories-through-your-commits/
https://tekin.co.uk/2019/02/a-talk-about-revision-histories

it connects with longevity of things: code > commits >> jira >> slack

------------------------


git archive!!!
    sometimes I need to ship my git repo to an EC2 and tar -czf contains all sorts of crap (test data, .git, .env etc.). Git archive is a godsend


------------------------

title: Getting out of trouble in git?

You need to understand git internals. THis is an epic talk. https://www.youtube.com/watch?v=fHLcZGi3yMQ

------------------------

## software

### ides

- I've been using [Visual Studio Code](https://code.visualstudio.com/) on and off for quite a while, but I still don't use any advanced features. Here's [a EuroPython talk](https://www.youtube.com/watch?v=6YLMWU-5H9o) on some of its advanced features (not just) related to Python.



------------------------

There are tons of useful extensions for Jupyter Lab, check them out. https://youtu.be/3pdrzhny9Lc

------------------------

zeppelin better for long running jobs
jupyter better for development (line numbers, autocomplete, help, shortcuts, ...)
zeppelin better for apache stuffs
zeppelin better for combining runtimes
jupyter more lightweight

----

### cli

https://www.youtube.com/watch?v=qmh7Uppd3x0&feature=share

Git
Do ker
Testing
Go
Py
Julia

Cli: tig, rg, loc, ncdu, vim, tqdm

ripgrep
https://www.youtube.com/watch?v=dnzaIeUgH_4

- data sci command line - wc, grep, cat, head, tail, tail -f, zcat, zgrep, python -m json.tool, jq?, sed, awk

https://www.wezm.net/technical/2019/10/useful-command-line-tools/
https://boyter.org/posts/my-list-of-useful-command-line-tools/

Todo: join?

Watch tree
Watch uniq sort

Tr, sed, awk, head, tail, grep, head -c

Grep performance doc

How uniq works

Gunzip -c

Conventions: h/help/man; streaming pipes; tools only do one thing

For each command show the pandas equivalent - head, tail, value counts

Sample, shuffle, split (for paralelisation, can be streamed)
Parallel

Ssh config

Head -c can be replaced with cut -c

Wc, du

Tmux

Fold?
Curl

Bonus: non-standard - jq, ripgrep, csvkit, tqdm, 

Pipeline - curl wikidata, gunzip, head, sed, jq


------------------------

title: proc pouzivam ripgrep

- I ran some API in Node.js and immediately saw some debugging messages popup, which I forgot to remove. I did a quick `rg console.log` to find out where I put these ad hoc calls.
- I needed to drop some columns in a database, but wasn't sure if they were used anywhere. `rg column_name` and then `rg -l column_name | xargs sublime` to inspect each
- I had some TODOs in my code - where exactly? I need to go through them before CR

------------------------

liquidprompt!

------------------------

title: command line wizard

This was excellent
https://www.youtube.com/watch?v=dnzaIeUgH_4

bat, ripgrep and hyperfine are amazing

the rest is as well

------------------------

### vim

I have very little set up, basically just incsearch

i use very little
gg, G, f, t, ;, /, %s, ctrl + f/b or d/u, d/c, y, v/V, ()


fzf via vim-plug and fzf https://github.com/junegunn/fzf.vim
    via https://www.youtube.com/watch?v=-I1b8BINyEw
    then map ctrl+p to open any file

        call plug#begin('~/.vim/plugged')
        Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
        Plug 'junegunn/fzf.vim'
        call plug#end()

        nnoremap <C-p> :GFiles<CR>
coc looks cool - also via vim-plug
    https://github.com/neoclide/coc.nvim

### tmux
bind e set -g synchronize-panes
	~/.tmux.conf
    lets you toggle pane synchronisation (see asottile's talk on tmux)


## hardware

I tend to think of the electronic world as purely digital, so it was rather refreshing to listen to [this podcast episode](https://hanselminutes.com/652/analog-computing-and-the-computer-of-the-tides-with-charles-petzold) on analog computers. Hanselminutes in general covers these fringe-sounding topics, I love it.


------------------------

tpu on a bike

https://www.youtube.com/watch?v=UmDeKDgFRj4&feature=share

------------------------


title: Radiolab bit flip

---

- I saw this quite a while ago, but I remember it being quite cool. Scott Hansleman is diabetic, but doesn't like the commercial hardware and software used to track his blood sugar level. [He talks at length about making is own, open device](https://www.youtube.com/watch?v=uNhYhlBQoEY), with a gazillion caveats, of course.


-----

- With all those cutting edge technologies, it's quite refreshing to listen to a podcast about [coding for the ZX Spectrum](https://hanselminutes.com/670/coding-for-the-zx-spectrum-and-netflixblack-mirrors-bandersnach-with-matt-westcott), specifically for an episode of Black Mirror (an excellent TV series, by the way).




## random

------------------------

https://www.youtube.com/watch?v=H62hZJVqs2o&feature=share

This is why I love Strange Loop. This is “a guy” talking about the Voyager probes and why they managed 40+ years of uptime. 

------------------------

------------------------

I finally know why emails end with J. It's Wingdings. Yes, really.

https://www.youtube.com/watch?v=SMSmKg1nApM

------------------------


EOF










copy stuff from my smda makefile - it's what i use for go anyway

ctrl z + fg

Some perf can be free in terms of cpu, if it’s memory bound

Compilers are awesome


---

- I like Joel Grus, he [live streams himself live coding Advent of Code](https://www.youtube.com/watch?v=VPXXthwAdg8&list=PLeDtc0GP5ICklPBnoZ0fdrw130hxI6_b3), he has written a cool book on Data Science (the second edition [has just been released](https://www.oreilly.com/library/view/data-science-from/9781492041122/)) and... he [doesn't like Jupyter notebooks](https://www.youtube.com/watch?v=7jiPeIFXb6U). It's a good thing that this is talked about, because notebooks are almost universally praised, but people should know about the downsides, too.

---


- The one and only Jake VanderPlas and [his tips and tricks regarding well performing numerical code in Python](https://www.youtube.com/watch?v=zQeYx87mfyw).

---





- I'm not a huge fan of dependencies, I like to have functionality baked into the runtime that I'm using and only choose a handful of must-have dependencies, I have my reasons. And I'm not the only one, [here's a good post](https://todd.ginsberg.com/post/the-art-of-picking-dependencies/) on picking dependencies responsibly.


---

- I've gotten into the habit of writing post mortems whenever I screw up. This came from reading [Dan Luu's writeup](https://danluu.com/postmortem-lessons/). There's also an accompanying repo with [a list of post mortems](https://github.com/danluu/post-mortems).
- This is a bit dated video [about the future of pandas](https://www.youtube.com/watch?v=_-gJtO0XR48) but some of it still applies and it goes to show that it's still evolving and that there are changes to come.
- We're all used to REST now, but GRPC is making strides. Here's [a good overview](https://youtu.be/RoXT_Rkg8LA) of how it differs from REST, WSDL, Thrift etc.
- [You are not Google.](https://blog.bradfieldcs.com/you-are-not-google-84912cf44afb) Sure, we all know that... but do we?

---
title: "Assorted tech links #7"
date: 2019-10-14T07:03:53+02:00
---


---

- Not everything has to be centralised. This is one of the rarest use cases for complex technology, Chick-fil-A installed Kubernetes at the edge, since the internet is unstable (plus a few other reasons). There's [an article](https://medium.com/@cfatechblog/edge-computing-at-chick-fil-a-7d67242675e2) and [a video with slides](https://www.infoq.com/presentations/chick-fil-a-k8-clusters).
- Lessons learned from [a Kubernetes outage at Monzo](https://www.youtube.com/watch?v=OUYTNywPk-s). And it's not the only Kubernetes post mortem, there's [a whole list of them](https://github.com/hjacobs/kubernetes-failure-stories).
- Crash early, crash often. [Good tips](https://medium.com/@mattklein123/crash-early-and-crash-often-for-more-reliable-software-597738dd21c5) from the author of [Envoy](https://www.envoyproxy.io/).
- [Linear models are awesome](https://youtu.be/68ABAU_V8qI), I’m glad someone can explain that with such rigour. Also, I thought I had too many slides, but I just witnessed Vincent go through 145 slides in 35 minutes.


---

- I tried out Presto for a few workloads and I was incredibly impressed. It's a great piece of software and [this video](https://www.youtube.com/watch?v=Z2C-iYNm2wU) offers a really nice overview of its architecture and how it differs from Spark.


http://veekaybee.github.io/2019/05/10/java8/

> Five years ago, if you gave a computer a pile of photos, it couldn’t do much more than sort them by size. A ten year old could sort them into men and women, a fifteen year old into cool and uncool and an intern could say ‘this one’s really interesting’. Today, with ML, the computer will match the ten year old and perhaps the fifteen year old. It might never get to the intern. But what would you do if you had a million fifteen year olds to look at your data? What calls would you listen to, what images would you look at, and what file transfers or credit card payments would you inspect?

> That is, machine learning doesn't have to match experts or decades of experience or judgement. We’re not automating experts. Rather, we’re asking ‘listen to all the phone calls and find the angry ones’. ‘Read all the emails and find the anxious ones’. ‘Look at a hundred thousand photos and find the cool (or at least weird) people’. 

[Here's an excellent PSA.](https://twitter.com/brendandburns/status/1007350396078075904)

------------------------

https://www.youtube.com/watch?v=4P_kbF0EbZM&feature=share

This is fadcinating https://youtu.be/kw-U6smcLzk

------------------------

https://www.youtube.com/watch?v=yvBR71D0nAQ&feature=share

------------------------
“Speed [of work] is not the goal, it’s a by product” 
https://youtu.be/w008iz_UwDk

------------------------

https://podcasts.apple.com/cz/podcast/the-changelog/id341623264?i=1000440755325

------------------------


https://www.youtube.com/watch?v=6Y5CZ7_tyA4&feature=share

------------------------

https://www.youtube.com/watch?v=kIoZDUd5DKw&feature=share

------------------------




------------------------

title: Geoshards, hilbert curves

Has part two
https://medium.com/tinder-engineering/geosharded-recommendations-part-1-sharding-approach-d5d54e0ec77a



title: Programming should be responsible

To the environment, to the people of the world (bandwidth) etc.

https://www.youtube.com/watch?v=JfjiFsJsO4E

------------------------



I tend to think of the electronic world as purely digital, so it was rather refreshing to listen to [this podcast episode](https://hanselminutes.com/652/analog-computing-and-the-computer-of-the-tides-with-charles-petzold) on analog computers. Hanselminutes in general covers these fringe-sounding topics, I love it.

http://veekaybee.github.io/2019/05/10/java8/

> Five years ago, if you gave a computer a pile of photos, it couldn’t do much more than sort them by size. A ten year old could sort them into men and women, a fifteen year old into cool and uncool and an intern could say ‘this one’s really interesting’. Today, with ML, the computer will match the ten year old and perhaps the fifteen year old. It might never get to the intern. But what would you do if you had a million fifteen year olds to look at your data? What calls would you listen to, what images would you look at, and what file transfers or credit card payments would you inspect?

> That is, machine learning doesn't have to match experts or decades of experience or judgement. We’re not automating experts. Rather, we’re asking ‘listen to all the phone calls and find the angry ones’. ‘Read all the emails and find the anxious ones’. ‘Look at a hundred thousand photos and find the cool (or at least weird) people’. 


Bryan Cantrill tends to get excited about stuff. Here he [talks about various languages](https://youtu.be/HgtRAbE1nBM) and why he likes Rust. Oh and [here as well](https://www.youtube.com/watch?v=2wZ1pCpJUIM). I also enjoyed his talk on [growing teams](https://www.youtube.com/watch?v=1KeYzjILqDo).

DynamoDB is amongst the better known NoSQL offerings, but being proprietary, we don't usually get to find out a lot about their architecture. Here, apart from [the Dynamo paper](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf), there's a nice architectural overview [from last year's AWS re:Invent](https://www.youtube.com/watch?v=yvBR71D0nAQ&feature=share).

------------------------

title: hash storage issues

screenshot!



------------------------

https://www.youtube.com/watch?v=NF0CY43GYKU&feature=share

---

https://www.youtube.com/watch?v=jvwfDdgg93E&feature=share

------------------------

https://www.youtube.com/watch?v=pNcB7ChyO1E

Accessibility is rather important and it doesn't take a PhD to do at least some things right. Here's a nice overview of some of the practices that make websites easier to browse by all.

------------------------



------------------------

This is a pretty nice tool for presenting POCs to non-technical users, in many ways similar to Voila (there’s a comparison near the end of the video). I especially like the embedding feature that leads to a serverless deployment. https://youtu.be/Ohr29FJjBi0

------------------------


https://www.youtube.com/watch?v=XelrzDtEnPY&feature=share

Dealing with dimensionality in an interesting way






------------------------

title: Ethics in sw

A great overview of ethical issues in software. Facebook, Tesla, Uber, Boeing, .... https://www.youtube.com/watch?v=0wtvQZijPzg

------------------------





------------------------

title: Shell minima

ripgrep
https://www.youtube.com/watch?v=dnzaIeUgH_4

liquidprompt!

alias

ctrl z + fg

------------------------


------------------------

title: harmonogram

 - "but the amount of brain bandwidth and dependencies to launch a modern web app is getting a bit absurd"  https://news.ycombinator.com/item?id=15380479
- Add to jupy tunneling https://t.co/r36imBuGAH?ssr=true
- open source is awesome https://github.com/golang/go/issues/20427
- https://news.ycombinator.com/item?id=15849662
- hash-based file store has one more disadvantage - no sequential scans or range queries, because keys are random
- hide jupyter visibility (block incoming 8888 from outer internets) for more security - against port scanning
- apache drill - ansi sql, can be embedded, has a clean UI, has jdbc, schema on read... what's not to love?
- explainable ML - http://multithreaded.stitchfix.com/blog/2017/10/18/stop-using-word2vec/
- models can be explainable! a great explanation of how they created explanations for random forests (https://www.youtube.com/watch?v=DiWkKqZChF0) - their collegaues previously talked about implementing these models at scale https://www.youtube.com/watch?v=vKU8MWORHP8
