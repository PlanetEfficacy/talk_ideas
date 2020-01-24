# Title
Microservice Misadventures

# Session Format
Regular Session

# Track

* [ ] Memorable Post-Mortems - Talks in this track will feature your favorite post-mortem stories, especially ones where you and your team learned a lot. Talks should delve into what happened, how it changed what you did going forward, and what lessons it could teach other developers.

# Abstract
##### A concise, engaging description for the public program. Limited to 600 characters.

Moving functionality from a majestic monolith to a microservice is hard.

Participants will learn about the mistakes I made while extracting functionality from a majestic monolith into a microservice so they do not have to repeat them in their own service architecture adventures, or better yet, skip the adventure altogether.

# Details
##### Include any pertinent details such as outlines, outcomes or intended audience.

## Argument
Microservice architecture promises system encapsulation, modularity, and team autonomy. However, this comes at the cost of complexity in the form of devops infrastructure and the proliferation of multiple frameworks and languages. Through my experience extracting a microservice from a Rails monolith I have come to agree with DHH's blog post "The Majestic Monolith," which argued that the only justification for microservice architecture is to fit the organizational needs of very large companies. Any other benefit can be achieved within a majestic monolith and at much less cost.

## Background Context
- I work at a company with ~600 employees, ~130 developers
- We have a Rails monolith that was created in 2012 and we have millions of users
- For about half the life of the company, there were fewer than 10 engineers. Rails empowered these engineers to move fast and iterate

## Why did we choose a microservice architecture
- Conway's Law - "Any organization that designs a system will inevitably produce a design whose structure is a copy of the organization's communication structure."
- The assumption that Rails was not the right tool for the job

## Microservice Misadventures
- Discuss key decisions we made, how they hurt us, and what we should have done instead

### Misadventure Decision 1: Let the new person pick the technology
#### Bad decision:
Our new teammate felt pretty strongly that we should be using Scala and Akka for this particular service and we compromised with Kotlin, Spring and Akka.
#### How did this decision hurt us:
Our teammate was the only person in the organization with any experience with Akka. Further more, our teammate decided to leave the team before the microservice was fully complete.
#### What we should have done instead:
Used Rails, Sinatra, or Java and Spring, technologies that are more prolific in our organization

### Misadventure Decision 2: Divide the Work by Application
#### Bad decision:
Our new teammate took on all of the stories for building the microservice. I took on all of the stories integrating the microservice with our existing monolith.
#### How did this decision hurt us:
This division of labor resulted in silo-ed knowledge. Neither of us had any idea how the other's system worked.
#### What we should have done instead:
Even though this would have slowed us down, we should have been working in both domains to prevent the silo-ing of knowledge

### Misadventure Decision 3: Premature Optimization
#### Bad decision:
There are so many examples of areas where we opted to preamaturely optimize our system rather than shipping an mvp.
- Implemented caching before we were even getting traffic
- Processing multiple data streams in parallel
- Overly complicated DDB tables tracking unnecessary info
- Trying to improve core business logic - in other words making too many changes at one time
#### How did this decision hurt us:
It was tough to debug mission critical functionality because of all of the unnecessary optimizations and features that laid groundwork for future features that either will likely never be developed.
#### What we should have done instead:
Replicated the smallest possible unit of value for the business and iterate.


## Pitch

##### Explain why this talk should be considered and what makes you qualified to speak on the topic.

Microservice misadventures is a talk that will offer lessons relevant to a wide variety of Railsconf participants. From CTO's setting the technology direction of their companies to brand new developers, who are contemplating moving to a service oriented architecture, to individual contributors about to pick up their first microservice story, this talk will describe mistakes that any team might find themselves making on their own microservice misadventure.



## Bio

##### Your bio should be short, no longer than 500 characters. It's related to why you're speaking about this topic.

Jesse Spevack is a father of twins, skier, marathoner, and Senior Platform Engineer at Ibotta, a cash back for shopping app whose mission is to *make every purchase rewarding*. Before getting into the tech world, Jesse worked in public K-12 education for 11 years in teaching, school leadership, and school consulting roles. Jesse transitioned from education into technology by way of the Turing School of Software Design, a Denver based code school with a Ruby-centric curriculum and deep ties to the Rails community.

----
