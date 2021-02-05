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


#### Software development

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


### Data

#### Architecture, engineering

I've been looking forward to Kafka dropping ZooKeeper and always viewed the change as just swapping a part. Turns out there are good reasons other than simplifying deployment. This is [a good talk on that](https://www.youtube.com/watch?v=3qNNinbnWmw). There's also [an article](https://www.confluent.io/blog/removing-zookeeper-dependency-in-kafka/), [a Confluence doc](https://cwiki.apache.org/confluence/display/KAFKA/KIP-500%3A+Replace+ZooKeeper+with+a+Self-Managed+Metadata+Quorum), and [a JIRA ticket](https://issues.apache.org/jira/browse/KAFKA-9119).

Millions of tiny databases - Amazon runs exabytes of storage for their customers and it turns out that running replicated storage reliably is quite hard and it calls for unorthodox solutions. [Paper](https://assets.amazon.science/c4/11/de2606884b63bf4d95190a3c2390/millions-of-tiny-databases.pdf)


title: Transparent Hierarchical Storage Management with Apache Kudu and Impala

https://blog.cloudera.com/blog/2019/03/transparent-hierarchical-storage-management-with-apache-kudu-and-impala/

------------------------

title: ongoing by Tim Bray · On Sharding

https://www.tbray.org/ongoing/When/201x/2019/09/25/On-Sharding

Sharding is hard

------------------------

https://www.youtube.com/watch?v=BuE6JvQE_CY&feature=share

Luckily the answer is not quite. 

law of headlines

------------------------

title: map reduce paper

the map reduce paper is super easy to read and there are tons of things I like about it
- it's driven by a real need (compute a lot of stuff)
- it uses commodity hardware, which later enabled thousands of developers worldwide to leverage the methodology
- they describe a system of backup tasks that fix the issue of outliers taking ages to complete
- they focus on the fact that the system allows for a much simplified computing model - people without the knowledge of distributed computing can write massively paralelised workloads - in a way it's similar to SQL

https://static.googleusercontent.com/media/research.google.com/en//archive/mapreduce-osdi04.pdf

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

-----------------

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

-----------------

title: Careful about pandas

https://www.youtube.com/watch?list=PLGVZCDnMOq0oqs6RTJk4zZde86DZrgnzm&v=_-gJtO0XR48

---------------------

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

title: We learned this the hard way

https://hakibenita.com/fast-load-data-python-postgresql


------------------------

title: pg 13

Interesting things coming to postgres 12, further partitioning improvements, better JSON support, but mainly some internal changes that allow for pluggable storage, which is likely to be user-facing in pg13 https://www.youtube.com/watch?v=VMLl-t4H_KI

------------------------

I’m a sucker for database internals talks. Here’s a very clear talk about InfluxDB - memory layout, on disk serialisation, compression, hashing.

https://www.youtube.com/watch?v=rtEalnKT25I&feature=emb_logo

---------------------

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

---------------------

title: postgres talks

Some rather good Postgres talks - more about data management than querying

indexing - what's out there apart from btree - https://www.youtube.com/watch?v=Xv0NFozBIbM

jsonb, its usage and indexing - https://www.youtube.com/watch?v=p9RItyeKbLQ

---------------------

title: BigQuery ML

A very good overview of how ML tools can be implemented in a massively scalable engine like BigQuery. https://www.youtube.com/watch?v=svQdwU3iPp8

---------------------

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

---------------------

title: 8 Major Improvements in PostgreSQL 12

https://www.enterprisedb.com/blog/8-major-improvements-postgresql-12

Cant wait to use pg12 - my fav is not mentioned though - generated columns

------------------------

#### text processing

------------------------

title: Fuzzy search

Pretty cool to see major performance wins in text similarity algos. Useful for clustering, fuzzy joins etc. I really liked the letter bitmap stuff. https://youtu.be/s0YSKiFdj8Q

------------------------

#### machine learning

- I'm not a huge fan of overhyped parts of ML/AI, so I welcomed [this sober post](https://www.ben-evans.com/benedictevans/2018/06/22/ways-to-think-about-machine-learning-8nefy).

- Learned indexes sound a bit like magic. Instead of being explicitly set up like regular indexes, these are inferred from data and can perform better. But it's better explain by one of the authors, [Tim Kraska](https://www.youtube.com/watch?v=mkIHC7xMSRQ) or perhaps [by Robert Rodgers](https://www.youtube.com/watch?v=0q9mxMekBeE).

- You don't have to have fancy math across all your slides, I much prefer clear talks with good examples. [Robert Rodger's talk on text summarisation](https://www.youtube.com/watch?v=VZ5BEKVxy9k) is just that. I actually saw this one live, it was great.

