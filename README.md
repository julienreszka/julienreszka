# Hi there 👋

## 9 Popular Programming Principles DEBUNKED

Contrary to popular belief, good programmers aren't lazy.

It may seem like they are because some of the most lazy programming principles have been widely adopted and celebrated in the programming community.

In fact, good programmers are often disciplined, methodical, and strategic in their approach. 

Let's explore some of the widely adopted programming principles that are debunked and rejected by experienced developers.

### ~Don't Repeat yourself (DRY)~ 

Tight coupling makes a system less flexible and harder to maintain.

**Repeat yourself.**

Generalize only after a threshold of repetition.

Duplications are less costly than wrong abstractions and there is never enough granularity.

Use global search to find all the places where something is used, use regex to be more effective in your search.

### ~Keep it simple stupid (KISS)~ 

Certain problems are inherently complex.

**Don't keep it simple stupid.**

Architecture it such it can be perfected.

It's highly unlikely that you will get it right on the first try so make sure you will be able to improve it on next iterations.

Use feature toggles to architecture your app in an extensible way.

### ~You Ain't Gonna Need It (YAGNI)~ 

Accumulating defects will inevitably lead to some kind of failure.

**You will probably need this.**

Recognize that Mistakes happen but also that Failure is not an option.

Make sure that if there are defects, they have a workaround and they are in secondary features.

Classify defects severity with "has_no_workaround" and "is_critical_component" flags.

### ~Fail Fast~ 

Failure is a significant drain on resources.

**Recover quickly.**

Develop mechanisms of control.

Crashing an airplane won't teach you as much as using a wind tunnel to fly a model in an environment that you can control.

Instead of returning immediately a single error, make an observable arrays of reasons to abort so that you can solve all at once instead of one by one.

### ~Read the fucking manual (RTFM)~

Manuals are often out of date.

**Don't rely on a manual.**

Make assertions to probe the system.

Help project maintainers make their code more intuitive by comparing how you expect the system to work and how it is actually working.

### ~Maintain UI consistency~

Trying to maintain UI consistency over time is a fool's errand.

**Don't reinvent the wheel**

Focus on the user experience.

It's ok if a UI component doesn't match the style of the app but makes things easier for the user because he already knows how to use it.

Write functional requirements that say what `a feature` `in a specific context` `allows or does not allow` `users with a certain role` `to do` `by doing what`.

### ~Be conservative in what you send, be liberal in what you accept (Postel's Law)~

Malicious actors exploit lax input validation to inject harmful code or manipulate protocols.

**Be conservative in both what you send and receive.**

Strict input and output validation improves interoperability by enforcing clear communication standards.

Sanitize data, Parameterize queries, use whitelists. 

### ~It always takes longer than you expect (Hofstadter’s Law).~

It's possible to make accurate estimates.

**Make realistic deadlines**

Breakdown tasks into 3 parts, the optimistic duration, the buffer for realistic duration, the buffer for pessimistic duration.

By sizing your degree of uncertainty for each task you will be able to tell whether more work should be done on the specifications and preliminary work.

### ~Premature Optimization is the root of all evil (Donald Knuth)~

Delaying optimization until later stages will lead to significant performance issues that are costly to rectify.

**Make fast benchmarking part of your development process.**

Focus your optimization efforts on on high level evaluations and long term functional requirements.

Look at the overall process before going into details.

## Favorite vs code extensions

1. [Todo tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
1. [i18n Ally](https://marketplace.visualstudio.com/items?itemName=Lokalise.i18n-ally)
