# Microservices

In any system that is worth building there is going to be some complexity, otherwise why is it being built in the first place?

The question really is where does that complexity end up and does that fundamentally make it easier to deal with.

## A Definition
The idea of a micro service is easiest to define as what it is not. It’s not a Service Oriented Architecture (SOA) in that it doesn’t seek to integrate business applications but more to build applications.

## Some Questions
Engineering is about trade offs otherwise its just a [golden hammer](https://en.wikipedia.org/wiki/Law_of_the_instrument)

* Why are you using them?
* What are the benefits for your specific problem?
* What are the costs/risks, there will be some?

## Risks and Costs
In any given project the advantages of a technology should be clear otherwise why the hell are you using it again? It’s worth enumerating a list of the risks and costs though as they can easily get missed until its too late.

* Complexity is moved to deployment/dev-ops, complexity of interfaces and contracts are no longer handled by the compiler. Don’t underestimate how much a compiler is doing for you.

* Added [latency](/rulesoftheroad.html), all of the communication will now be going through the networking stack. If its all on the same machine it will be faster, but if that is the case why is it doing it at all?

* Versioning becomes a deployment problem, how do you know what version of an interface you are talking to? Can you do a rolling deployment?

* Networking complexity inside the application as well as outside.  [Distributed computing is hard](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)

## In Summary
There are definite benefits to be had from Restful Micro-services, it’s important to keep in mind the costs though.