# Title
Mistakes Were Made

# Session Format
Regular Session

# Track

* [ ] Memorable Post-Mortems - Talks in this track will feature your favorite post-mortem stories, especially ones where you and your team learned a lot. Talks should delve into what happened, how it changed what you did going forward, and what lessons it could teach other developers.

# Abstract
##### A concise, engaging description for the public program. Limited to 600 characters.
We picked the wrong technology. We worked in silos. We prematurely optimized. We introduced too many changes at once. And yet somehow we delivered a system that is integral to a shopping rewards app used by millions across the United States. I want to tell you the story of how the best of intentions led to crucial blunders. In this public, honest, and vulnerable post-mortem I will share the missteps I made so that you can avoid them.

# Details
##### Include any pertinent details such as outlines, outcomes or intended audience.

## Argument

Even the best of intentions can lead us to make mistakes.

## Background Context
- I work at a company with ~600 employees, ~130 developers
- We have a Rails monolith that was created in 2012 and we have millions of users
- For about half the life of the company, there were fewer than 10 engineers. Rails empowered these engineers to move fast and iterate
- Why this project? Conway's Law - "Any organization that designs a system will inevitably produce a design whose structure is a copy of the organization's communication structure."

- Discuss key decisions we made, what was the intent, how they hurt us, and what we should have done instead

### Mistake 1: Picking the wrong technology

#### Bad decision and Intention:
Our new teammate felt strongly that we should be using Scala and Akka for this particular service and we compromised with Kotlin, Spring and Akka. Our intent here was to include the new teammate that we were excited to have on board. We wanted to validate this teammate's experience and make them feel like they were making big decisions and contributing from day one.

#### How did this decision hurt us:
Our teammate was the only person in the organization with any experience with Akka. Further more, our teammate decided to leave the team before the microservice was fully complete.

#### What we should have done instead:
Used Rails, Sinatra, or Java and Spring, technologies that are more prolific in our organization

### Mistake 2: Divide the Work by Application

#### Bad decision and Intention:
Our new teammate took on all of the stories for building the microservice. I took on all of the stories integrating the microservice with our existing monolith. Our intention here was to move fast. We wanted to deliver this project early so that we could move on to the next project.

#### How did this decision hurt us:
This division of labor resulted in silo-ed knowledge. Neither of us had any idea how the other's system worked.

#### What we should have done instead:
Even though this would have slowed us down, we should have been working in both domains to prevent the silo-ing of knowledge

### Mistake 3: Premature Optimization

#### Bad decision and Intention:
There are so many examples of areas where we opted to prematurely optimize our system rather than shipping an mvp.
- Implemented caching before we were even getting traffic
- Processing multiple data streams in parallel
- Overly complicated dynamo DB tables tracking unnecessary info

Of course the intention with premature optimization is to optimize. We wanted a highly performant system, but we ended up getting way ahead of ourselves.

#### How did this decision hurt us:
It was tough to debug mission critical functionality because of all of the unnecessary optimizations.

#### What we should have done instead:
Added optimizations as needed once the system was completely rolled out.

### Mistake 4: Making too many changes at once

#### Bad decision and Intention:
This feature relied on both new input data and new processing with the goal of arriving at the same result. We changed both input data and our algorithm for processing the data at the same time. Our intention here was to have a more reliable and trusted data source as well as more accurate processing.
- Trying to move and improve core business logic - in other words making too many changes at one time

#### How did this decision hurt us:
It was much, much harder to verify each step of our system was working and could be trusted because multiple pieces were being changed simultaneously.

#### What we should have done instead:
Replicated the smallest possible unit of value for the business and iterate. We should have first started with the input data and verified it against the old data. Then we should have copied the original algorithm exactly to again verify everything was working before moving forward.

## Pitch

##### Explain why this talk should be considered and what makes you qualified to speak on the topic.

Mistakes Were Made is a talk about how good intentions are not enough to prevent mistakes. This story will offer lessons relevant to a wide variety of Railsconf participants. From CTO's setting the technology direction of their companies to individual contributors about to dive into a new major project, this talk will describe mistakes that any team might make as well as tips for avoiding them.

I am excited to give this talk for a few reasons. For starters, I have first hand experience leading a squad of engineers through the work of planning and executing on a project. Next, I am prepared to be open about the mistakes that I made in this process so that the Rails community does not have to repeat them. Finally I think I have the presentation skills to share this experience in an engaging and informative manner given my background as a teacher in k12 public education and previous public speaking events.

I love the idea of a post mortem track because failure is feedback. Failure is an amazing teacher. I learned so much over the course of this project and I am a much better developer for having gone through this experience. I am eager to share this with my Railsconf brothers and sisters so that hopefully I can help them avoid making these same mistakes.

## Bio

##### Your bio should be short, no longer than 500 characters. It's related to why you're speaking about this topic.

Jesse Spevack is a father of twins, skier, marathoner, and Senior Platform Engineer at Ibotta, a cash back for shopping app whose mission is to make every purchase rewarding. Before getting into the tech world, Jesse worked in public K-12 education for 11 years in teaching, school leadership, and school consulting. Jesse transitioned from education into technology by way of the Turing School of Software Design, a Denver based code school with a Ruby-centric curriculum and deep ties to the Rails community.

----
