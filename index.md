# Rules of the road

gwaan

I like simple guidelines. They are training wheels, just there to stop me falling on my face.

## General Architecture

Do the work on write/update wherever you can.

Flat file sites are FAST

Caches are bad, if you must cache then let http do it for you. Then the data source retains control of its data with a load consistency trade off.

Avoid using JavaScript without a very good reason.

If you must use JS then it should only be for personalisation and client side composition.

Micro services move the complexity from compile time to deployment time. Are you smarter than a compiler? (There’s probably ways round this, something like a web machine meta-model could map to amazon lambda)

### State

Where is the state? If you’re doing anything of use there must be persistence somewhere. Understand the scope of the persistence. It’s actually what defines the boundaries of the service.

Queue’s count as state. (In a way persistence is queues, or at least order, see linearisation)

### Communication

Make communication explicit. If two systems communicate make sure it is understood and not implicit through a database or some other storage medium.

Communication should be decoupled wherever possible, contracts.

If things are very closely coupled or even really chatty then they should probably be in the same process and any complexities controlled by a compiler.

Bandwidth Delay/Latency Product: You can have all the bandwidth in the world but latency will kill you most of the time. See notes

### Brewers CAP Theorem (Eric Brewer)

* Consistency (all nodes see the same data at the same time)
* Availability (a guarantee that every request receives a response about whether it succeeded or failed)
* Partition tolerance (the system continues to operate despite arbitrary partitioning due to network failures)

Pick any two. Its more complicated than that though. (CAP is uncool now)

## Security

Don’t do your own cryptography, ever.

Careful with the keys. 

Security is very very hard don’t reinvent the wheel. 

Consider the difference between Authentication and Authorisation.

If you need an audit trail that isn’t trivial then consider an event store. If that’s too complex then consider a command model, every request is a command that gets logged as run or failed. Depends on the purpose of the audit trail. 

## Non Functional Requirements

Do you have non functional requirements. If so can you test that they are being met?

What are the dimensions: Request, Storage, Response Time, Transactions etc. Lots of users isn’t a dimension.

If they doubled what would happen, what about an order of magnitude.

Always prototype with real infrastructure.

## Monitoring

Start with errors and work up from there.

With something that looks like REST you can get a very useful log just from the HTTP log. 

Aggregate information somewhere and start graphing and alerting.

## Code

Management of complexity is everything. 6 dice as a system, 6^6 combinations, untestable. 1 die only has six states.

* Strings are bad
* Side effects are bad
* Reusability is overrated
* So is inheritance
* Lean on the compiler
* The more dynamic the language the more you need tests to exercise the code
* Strings are bad, repeated for effect.
* Use languages from the 70s, not the 60s

Small systems do not have to mean micro-services. Can be code modules, libraries etc.

## Latency Comparison Numbers

L1 cache reference                           0.5 ns

Branch mis-predict                           5   ns

L2 cache reference                           7   ns                      14x L1 cache

Mutex lock/unlock                           25   ns

Main memory reference                      100   ns                      20x L2 cache, 200x L1 cache

Compress 1K bytes with Zippy             3,000   ns        3 us

Send 1K bytes over 1 Gbps network       10,000   ns       10 us

Read 4K randomly from SSD*             150,000   ns      150 us          ~1GB/sec SSD

Read 1 MB sequentially from memory     250,000   ns      250 us

Round trip within same datacenter      500,000   ns      500 us

Read 1 MB sequentially from SSD*     1,000,000   ns    1,000 us    1 ms  ~1GB/sec SSD, 4X memory

Disk seek                           10,000,000   ns   10,000 us   10 ms  20x datacenter roundtrip

Read 1 MB sequentially from disk    20,000,000   ns   20,000 us   20 ms  80x memory, 20X SSD

Send packet CA->Netherlands->CA    150,000,000   ns  150,000 us  150 ms


#### Credit
By Jeff Dean:http://research.google.com/people/jeff/
Originally by Peter Norvig: http://norvig.com/21-days.html#answers
https://gist.github.com/hellerbarde/2843375
