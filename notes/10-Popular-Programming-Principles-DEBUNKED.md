# 10 Popular Programming Principles DEBUNKED

Contrary to popular belief, good programmers aren't lazy.

It may seem like they are because some of the most lazy programming principles have been widely adopted and celebrated in the programming community.

In reality, those principles were widely adopted because there are a lot of lazy and bad programmers out there.

In fact, good programmers are often hard working, disciplined, methodical, and strategic in their approach.

Let's explore some of the widely adopted programming principles that are debunked and rejected by experienced developers.

## ~Don't Repeat yourself (DRY)~

Tight coupling makes a system less flexible and harder to maintain.

If two things look the same today it doesn't mean they will look the same tomorrow. 

Most likely they will diverge in upcoming versions.

**Repeat yourself.**

WET: Write everything twice

Generalize only after a threshold of repetition.

Duplications are less costly to modify and adjust than abstractions and there is never enough granularity.

Use comments to Lists places where similar code is in use and attach an identifier to make it easier to search for duplicates.

Use global search to find all the places where something is used, use regex to be more precise and effective in your search.

## ~Keep it simple stupid (KISS)~

Certain problems are inherently complex.

**Don't keep it simple stupid.**

PUSH: Perfect Until Sufficiently Honed

Architecture your functionalities such that they can be perfected.

It's highly unlikely that you will get it right on the first try so make sure you will be able to improve it on next iterations.

Use feature toggles to architecture your app in an extensible way.

## ~You Ain't Gonna Need It (YAGNI)~

Accumulating defects will inevitably lead to some kind of failure.

**You will probably need this.**

Recognize that Mistakes happen but also that Failure is not an option.

Make sure that if there are defects, they have a workaround and they are in secondary features.

Classify defects severity with "has_no_workaround" and "is_critical_component" flags. 

The more flags checked, the more severe the defect.

## ~Fail Fast~

Failure is a significant drain on resources.

**Recover quickly.**

Develop mechanisms of control.

Crashing an airplane won't teach you as much as using a wind tunnel to fly a model in an environment that you can control.

Instead of returning immediately a single error, make an observable arrays of reasons to abort so that you can solve all at once instead of one by one.

## ~Read the fucking manual (RTFM)~

Manuals are often out of date.

**Don't rely on a manual.**

Make assertions to probe the system.

Help project maintainers make their code more intuitive by comparing how you expect the system to work and how it is actually working.

### For example:

Let's consider the documentation for a widely-used open-source project, like Git, the version control system. Over time, Git has had comprehensive documentation, but it's a complex tool that undergoes updates and changes. As a result, some aspects of the documentation might not always perfectly align with the latest version or might lack details on newer functionalities.

For instance, imagine a scenario where the Git documentation hasn't been updated to include a newly introduced command that simplifies the process of reverting changes within a repository. The manual might still suggest a more convoluted approach that was standard before the introduction of this newer, more efficient command.

In such a case, relying solely on the manual might lead users to follow outdated or less efficient procedures. However, proactive exploration and testing within the Git system could reveal this new command and its functionalities. Users who delve into the system and compare their expectations of functionality based on the manual with the actual capabilities of the updated Git version might notice discrepancies.

These users could then contribute by informing the maintainers about the missing or outdated information in the documentation. By doing so, they help the maintainers update the manual, ensuring that it accurately reflects the current features and capabilities of the Git system. This, in turn, assists other users who rely on the documentation to utilize the latest and most efficient tools available within Git.

## ~Maintain UI consistency~

Trying to maintain UI consistency over time is a fool's errand.

**Don't reinvent the wheel**

Focus on the user experience.

It's ok if a UI component doesn't match the style of the app but makes things easier for the user because he already knows how to use it.

Write functional requirements that say what `a feature` `in a specific context` `allows or does not allow` `users with a certain role` `to do` `by doing what`.

### For example 

Breaking down the YouTube UI into components might look like this:

#### Components of YouTube UI:
1. **Header**: Contains the search bar, YouTube logo, and navigation links.
2. **Sidebar**: Displays subscription channels, library, and trending videos.
3. **Video Player**: Displays the selected video along with playback controls.
4. **Comments Section**: Allows users to view and post comments.
5. **Recommendation Section**: Displays recommended videos based on user activity.
6. **Channel Information**: Shows details about the channel hosting the video.

#### Functional Requirements:

1. **Header**:
   - **Allows** all users to search for videos **by typing keywords** into the search bar.
   - **Does not allow** unauthorized users to access creator studio settings.
   
2. **Sidebar**:
   - **Allows** logged-in users to access their subscription channels and manage playlists.
   - **Does not allow** users without an account to view subscription content.

3. **Video Player**:
   - **Allows** all users to play, pause, and control the volume of the video being watched.
   - **Does not allow** users to download the video directly from the player.

4. **Comments Section**:
   - **Allows** logged-in users to post comments and replies on the video.
   - **Does not allow** users with a viewer role to delete other users' comments.

5. **Recommendation Section**:
   - **Allows** all users to view recommended videos based on their watch history.
   - **Does not allow** users to disable the recommendation feature entirely.

6. **Channel Information**:
   - **Allows** users to view details about the channel, such as subscriber count and description.
   - **Does not allow** users to edit channel information without proper permissions.

Each requirement specifies what a specific component allows or does not allow for users in certain roles within the context of using the YouTube interface.

## ~Be conservative in what you send, be liberal in what you accept (Postel's Law)~

Malicious actors exploit lax input validation to inject harmful code or manipulate protocols.

**Be conservative in both what you send and receive.**

Strict input and output validation improves interoperability by enforcing clear communication standards.

Sanitize data, Parameterize queries, use whitelists.

### For example:

Let's consider a scenario involving a web application that interacts with a backend database. One common vulnerability is SQL injection, where malicious SQL commands are injected into input fields to manipulate the database.

Suppose there's a login page where users input their credentials. Without proper validation, a malicious user could enter something like this into the username field:

```sql
' OR '1'='1
```

If the application doesn’t validate or sanitize this input properly, it might construct a SQL query like:

```sql
SELECT * FROM users WHERE username = '' OR '1'='1' AND password = 'input_password';
```

In this case, because '1'='1' always evaluates to true, the query would return a result, allowing the attacker to log in without a valid username and password combination.

To prevent this, the application should implement parameterized queries:

```sql
SELECT * FROM users WHERE username = ? AND password = ?;
```

The application then fills in the placeholders with the provided username and password values. This prevents the user input from being directly interpreted as SQL code and avoids the risk of injection attacks.

Additionally, input validation and sanitization techniques should be applied. For instance, the application should validate that the username contains only permissible characters (such as alphanumeric characters) and doesn’t contain any SQL commands or special characters that might be used for injection.

Implementing these measures—parameterized queries, input validation, and data sanitization—helps prevent malicious users from exploiting vulnerabilities and ensures a more secure interaction between the application and the backend database.

## ~It always takes longer than you expect (Hofstadter’s Law).~

It's possible to make accurate estimates.

**Refine your estimates as you refine your specifications by sizing your pessimism**

Make a Work Breakdown Structure (WBS).

Breakdown a project into components and subcomponents.

Do not break it down into tasks. Here we're talking about "definitions of done" not tasks.

Each deepest subcomponent break it down into 3 parts:
- the optimistic duration, the duration it will take to make if everything goes smoothly, no mistakes, no uncertainties
- the buffer for realistic duration, the additional duration it will take to fix eventual mistakes
- the buffer for pessimistic duration, the additional duration caused by uncertainty and lack of clarity in specifications

By sizing your degree of pessimism and therefore uncertainty for each livrable you will be able to tell whether more work should be done on the specifications and preliminary work to reduce this pessimism.

### For Example:

```
- [ ] A 390 min
  - [ ] AA 145 min
    - [ ] AA optimistic duration 100 min
    - [ ] AA realistic buffer 15 min
    - [ ] AA pessimistic buffer 30 min
  - [ ] AB 245 min
    - [ ] ABA 45 min
      - [ ] ABA optimistic duration 30 min
      - [ ] ABA realistic buffer 5 min
      - [ ] ABA pessimistic buffer 10 min
    - [ ] ABB 60 min
      - [ ] ABB optimistic duration 40 min
      - [ ] ABB realistic buffer 10 min
      - [ ] ABB pessimistic buffer 10 min
    - [ ] ABC 140 min
      - [ ] ABCA 60 min
        - [ ] ABCA optimistic duration 40 min
        - [ ] ABCA realistic buffer 10 min
        - [ ] ABCA pessimistic buffer 10 min
      - [ ] ABCB 80 min
        - [ ] ABCB optimistic duration 60 min
        - [ ] ABCB realistic buffer 10 min
        - [ ] ABCB pessimistic buffer 10 min
```

In this example we can see that sometimes the pessimistic buffer is even larger than the realistic buffer. This subcomponent should be investigated for potential specifications improvements.

If the clarification of the specifications takes longer than the pessimistic buffer, maybe it's not worth it to clarify and just go with common sense.

## ~Premature Optimization is the root of all evil (Donald Knuth)~

Delaying optimization until later stages will lead to significant performance issues that are costly to rectify and will lead to product market fit failure.

**Make fast benchmarking part of your development process.**

Focus your optimization efforts on high level evaluations and long term functional requirements.

Look at the overall process before going into details. 

Make use of:
- speed tests, time to execute certain operations
- load tests, responses to different levels of activity
- scalability tests, resource usage as activity grows
- stress tests, stability as we get closer to the edge
- reliability tests, consistency over time

### For example

Let's consider the development of a website for an e-commerce platform. In this scenario, the team delays optimization until the later stages of development.

Initially, the focus is on creating a functional website that allows users to browse products, add items to their cart, and proceed to checkout. The team works on designing the user interface, implementing basic functionality, and ensuring that the website works as intended.

However, optimization for performance is not a priority during this phase. As the development progresses, more features are added, such as user reviews, personalized recommendations, and integration with third-party services.

As the website nears completion, the team starts testing and realizes that the site is loading slowly. Page load times are high, especially when there's a peak in user traffic. Users experience delays when accessing product pages or navigating between different sections of the site.

Upon investigation, it's discovered that the website's code is not optimized. Images are not properly compressed, resulting in larger file sizes that slow down page loading times. The code for fetching and displaying product information is inefficient, causing delays in rendering pages. Additionally, the database queries are not optimized, leading to slow retrieval of information.


Customers don't go through the whole purchasing process even though it is possible because they are used to faster load times.

The consequence is that the competition is beating them on every metric because the laggy website causes a very high bounce rate: visitors leave the page.

Now, to rectify these performance issues, the team needs to conduct a thorough optimization process. They have to compress images, refactor code to improve efficiency, optimize database queries, and possibly even redesign certain functionalities to enhance performance.

This optimization phase becomes time-consuming and costly. The team needs to allocate resources to rework various aspects of the website to make it more responsive and faster for users. Moreover, during the period of slow performance, the website might have lost potential customers who were deterred by the sluggish user experience.

Had the team incorporated benchmarking and optimization practices early in the development process, they could have identified these performance bottlenecks sooner. By focusing on high-level evaluations and considering long-term functional requirements, they could have built a more optimized and responsive website from the outset, avoiding the need for extensive rework and delivering a better user experience from the start.

## ~The less it knows the better (Law of Demeter)~

Writing wrappers to satisfy LoD always leads to significant performance and maintainability issues.

**Create a single entry point**

Prefer the Facade pattern which provides a cleaner, more intuitive interface to interact with complex systems, ultimately improving both performance and maintainability of the codebase.
