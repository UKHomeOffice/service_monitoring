# Service Monitoring

This is a repository to help standardise on a way of approaching monitoring,
so that we have consistency as well as homing in on important specifics resulting
in useful and effective monitoring. 

All of this information is taken from SRE, (Site Reliability Engineering), by google and their lessons / approaches used.

## Issues with Monitoring

A lot of time people approach monitoring at the tool end as oppose at the development cycle. This usually, despite best efforts; tends to be a last minute approach in producing dashboards / alerts within whatever tool provided and tweaking throughout the lifecycle. This tends to lack any real structure about what you are monitoring and why. What does the business care about? What do you care about, enough to be called up in the middle of the night? 

Without the approach being considered upfront, new features may lack monitoring or some features may go unmonitored completely, despite it offering functionality to users. 

## Adoption

We have taken core aspects of SRE principles, but thought through it's application at development time. As we already have BDD (Behavior Driven Development), we want to establish how to apply monitoring to those principles as you iterate on a service.

It's important for us to note that there will be varying users that may not be a user of a normal BDD scenario, so we need to fulfil all aspects as part of the same principles as BDD, despite it not being specific to a user journey. This means knowing about aspects of things that might impact or be about to impact some functionality of that service, before it happens.

## Service Level Object

As mentioned above, we have taken the adoption and focused it towards BDD. With this in mind, we would expect certain objectives about a service to be driven by that scenario. You would also have an overall object of that service, that might mean you focus more on specific scenarios more than others i.e. losing partial functionality in some areas may not be deemed too critical to the serivce than others.

Once you select the objectives for each scenario we can then drive the metrics i.e.
- A user would log on (<1s with x amount of concurrent users)
- A user would then search and get a paginated response within x period (define what the period would be, would you expect this to be per data set size?)

## Four Golden Signals

The four golden signals are core monitoring categories that help focus on specifics on what to monitor. These are:
- **Latency**
  The time it takes to serve a request
- **Traffic**
  Transactions / retrievals per second or HTTP requests
- **Errors**
  Number of errors received, either via codes or missing headers you'd expect etc.
- **Saturation**
  How "full" your service is i.e. memory constrained / CPU constrained.

We would expect these to be applied to the BDD scenarios we create as mentioned above in the SLO (Service Level Object), we would then expect indicators to drive the specifics of what you are looking at.  

## Service Level Indicator

A defined measurement of some aspect of the level of service
- How many errors a service can have to meet an SLO
- How much latency can you deal with and number of errors for a logon to take the SLO period you've defined for that amount of users. 


