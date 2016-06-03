# Market Based Compute Resource Allocation

A.K.A Cost per call API’s

## What this is not
This is not cross charging, the rest of the organisation should have no visibility of this.

## What it is
A means of identifying which services are providing relatively little benefit for the amount of compute they consume. Also a means of focusing teams on the resources that they use, either directly or indirectly.

## How it works
The [21.co](https://21.co/mkt/) have implemented a marketplace for API’s that charge per call. Instead of a monthly subscription to that service usage is charged strictly per usage and is embedded in the call itself. This is computation as a commodity in its purest form. If another API provides the same functionality for less money then the obvious choice would be to use the alternative.

Inside a large organisation calls to services have costs that are not easily surfaced but fundamentally it all comes down to compute of some sort. Consider compute (c) to be some abstraction of CPU Cycles, Storage and Ram. Essentially, resources that could be used elsewhere.

The core of this idea is that all API calls inside an organisation should incur a cost to the project team that runs each service. The resources that they use providing their own service will also cost them depending on what they are using at any given time.

## Some Examples

* **Website Service**: Doesn’t use that much resource directly to run but makes a large number of calls to other services. It provides value to the business though so is given some (c) per month cover its operations.

* **Product Specific Service**: This would be a service that provides logic and storage based around a particular context. A typical micro service essentially. It will use storage and compute directly, make outgoing calls that cost. To counter outgoings it will have incoming calls and will need to set its cost per call accordingly.

* **Core Shared Service**: A resource intensive service that consumes a large amount of (c) running itself. To offset that it has a large number of incoming calls that it prices to pay for the resources used.

* **Legacy Service**: An older service unable to flex with demand that is called by a number of other services. Each call is highly priced due to its inability to flex.

Every project and its services will have a ledger that gives balance over any given period. Any service that is in the red will need to either charge more per call or justify the allocation of more (c) from the business.

*Compute is given to the projects by the business and back to the business for the computation that it provides*. Essentialy the projects are paying for the platform.

## Some Scenarios

* **Green Field**: A project is given some budget to get started, they use that initial allowance to create a test environment. They discover that compute is much cheaper in the evenings (think unused reserve instances) as there are pools of unused resource. As a result they decide to run performance tests overnight instead of through the day.

* **API Migration**: A service wants to move consumers off an older version of its API, so it charged more (c) for use of that and uses it to subsidise the newer version thus motivating the change and saving the team the effort of maintaining two versions in parallel.

* **Legacy Service Decommission**: A new service is created that can flex with load and as a result can charge a much lower rate per call. All of the consumers naturally move across.

* **Sensible API Use**: Projects that call API’s in wasteful ways, e.g. repeated unnecessary calls, are penalised for their poor implementation.

## Forcing Change

This system would make it possible to force change internally wither by adding a tax to certain services, personally I disagree with this but its an obvious option.

The other more interesting option is to gradually remove (c) from the system and leave it to the market place to work out how to allocate resources accordingly.

## Enforcement

Realistically an organisation isn’t going to turn off a service that is in the red. But they could certainly reward any service that was obviously extremely efficient.
