# Hi there 👋

## Programming principles debunked

### ~Don't Repeat yourself (DRY)~ 

Tight coupling makes a system less flexible and harder to maintain.

**Repeat yourself.**

Generalize only after a threshold of repetition.

Duplications are less costly than wrong abstractions.

### ~Keep it simple stupid (KISS)~ 

Certain problems are inherently complex.

**Don't keep it simple stupid.**

Architecture it such it can be perfected.

It's highly unlikely that you will get it right on the first try so make sure you will be able to improve it on next iterations.

### ~You Ain't Gonna Need It (YAGNI)~ 

Accumulating defects will inevitably lead to some kind of failure.

**You will probably need this.**

Recognize that Mistakes happen but also that Failure is not an option.

Make sure that if there are defects, they have a workaround and they are in secondary features.

### ~Fail Fast~ 

Failure is a significant drain on resources.

**Slow but steady.**

Develop mechanisms of control.

Crashing an airplane won't teach you as much as using a wind tunnel to fly a model in an environment that you can control.

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

### ~Be conservative in what you send, be liberal in what you accept (Postel's Law)~

Malicious actors exploit lax input validation to inject harmful code or manipulate protocols.

**Be conservative in both what you send and receive.**

Strict input and output validation improves interoperability by enforcing clear communication standards.

### ~It always takes longer than you expect (Hofstadter’s Law).~

It's possible to make accurate estimates.

**Breakdown tasks into 3 parts, the optimistic duration, the buffer for realistic duration, the buffer for pessimistic duration.**

By sizing your degree of uncertainty for each task you will be able to tell whether more work should be done on the specifications and preliminary work.

## Favorite vs code extensions

1. [Todo tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
1. [i18n Ally](https://marketplace.visualstudio.com/items?itemName=Lokalise.i18n-ally)
