# 10 Popular Programming Principles DEBUNKED

Contrary to popular belief, good programmers aren't lazy.

It may seem like they are because some of the most lazy programming principles have been widely adopted and celebrated in the programming community.

In reality, those principles were widely adopted because there are a lot of lazy and bad programmers out there.

In fact, good programmers are often hard working, disciplined, methodical, and strategic in their approach.

Let's explore some of the widely adopted programming principles that are debunked and rejected by experienced developers.

## ~Keep it simple stupid (KISS)~

In theory, simple solutions are easier to understand and maintain.

In practice, they are often too simplistic and fail to address the complexity of real-world problems.

Kelly Johnson's Keep it simple stupid principle was supposed to be a principle for sales to avoid technical and obscuring language when selling complex products. It was never intended to be an engineering principle. (see also: [10 Popular Sales principles DEBUNKED](10-Popular-Sales-Principles-DEBUNKED.md#use-simple-language))

The SR71 Blackbird is a perfect example of a complex product that was sold using simple language. It was the fastest plane ever built and it was sold to the US military as a plane that could fly from New York to London in less than 2 hours.

### Don't keep it simple stupid.

PUSH: Perfect Until Sufficiently Honed

Architecture your functionalities such that they can be perfected.

It's highly unlikely that you will get it right on the first try so make sure you will be able to improve it on next iterations.

Use feature toggles to architecture your app in an extensible way.

### For example

Let's say we're making a messaging app.

Here's what KISS would preconise.

```js
// Simple messaging app implementation
function sendMessage(message) {
  // Code to send the message
  console.log(`Sending message: ${message}`);
}

sendMessage("Hello, world!"); // Initial implementation
```

Here's what it should look like instead with PUSH.

```js
// Feature toggle flags
const encryptionEnabled = true;
const formattingEnabled = true;

// Function to encrypt the message
function encryptMessage(message) {
  // Simulated encryption logic
  return `Encrypted: ${message}`;
}

// Function to format the message
function formatMessage(message) {
  // Simulated formatting logic
  return `Formatted: ${message}`;
}

// Function to send a message with optional encryption and formatting
function sendMessage(message) {
  let processedMessage = message;

  if (encryptionEnabled) {
    processedMessage = encryptMessage(processedMessage);
  }

  if (formattingEnabled) {
    processedMessage = formatMessage(processedMessage);
  }

  // Simulated sending of the processed message
  console.log(`Sending message: ${processedMessage}`);
}

// Initial message without encryption and formatting
sendMessage("Hello, world!");

// Later iteration: toggling features
encryptionEnabled = false; // Disable encryption
formattingEnabled = true; // Enable formatting

// Sending a message with updated feature toggles
sendMessage("Goodbye, world!");
```

### Real life example of the disastrous consequences of following the keep it simple stupid principle

#### Therac-25 accidents

The Therac-25, a radiation therapy machine used in the 1980s for cancer treatment, was involved in at least six accidents between 1985 and 1987, in which patients were given massive overdoses of radiation. Three of these accidents resulted in the death of the patient, and the other three caused serious injury.

Due to a focus on simplicity and reusing software from a previous model, it had a software flaw that caused severe radiation overdoses in several patients.

The engineers adopted a "keep it simple" approach and reused software components from an earlier version of the machine.

This decision overlooked potential issues arising from the different operational modes of the new machine.

As a result, a race condition occurred in the software. When operators quickly input commands, the machine could deliver radiation doses that were orders of magnitude higher than prescribed.

The Therac-25 accidents are a prime example of the dangers of oversimplification. The engineers focused on reusing existing software components to save time and effort, but this led to a critical flaw in the system.

It costed multiple lives, the company, and Atomic Energy of Canada Limited (AECL), faced lawsuits and out-of-court settlements due to these accident.

After the accidents, in 1988 AECL dissolved the AECL Medical section and the company Theratronics International Ltd took over the maintenance of the installed Therac-25 machines.

It was not the only reason why the machine failed but it is one of the reasons.

#### Year 2000 problem (Y2K)

The Year 2000 problem, also known as the Y2K bug, was a computer flaw that affected many systems worldwide. The issue stemmed from the practice of representing years with two digits instead of four, (Foe example 1973 was 73) which caused confusion when transitioning from 1999 to 2000. Many systems interpreted the year 2000 as 1900, leading to incorrect calculations and data errors. The Y2K bug had the potential to disrupt critical infrastructure, financial systems, and other essential services. The problem was a result of oversimplification in early computer programming, where memory and storage limitations led to the use of two-digit year representations. The Y2K bug required extensive remediation efforts to update software and systems to handle four-digit year formats. The cost of addressing the Y2K bug was estimated to be billions of dollars, and the potential impact of widespread system failures prompted global concern and preparation. The Y2K bug serves as a cautionary tale about the consequences of oversimplification in software development.

#### Zoom Security and Privacy Issues (2020)

As the COVID-19 mass hysteria led to a surge in remote work and online meetings, the video conferencing platform Zoom faced scrutiny over various security and privacy flaws.

Issues included "Zoombombing" incidents (unauthorized users joining meetings), encryption concerns, and data sharing with Facebook without user consent.

Zoom had initially prioritized ease of use over robust security measures, resulting in these vulnerabilities.

The company had to issue public apologies and commit to releasing multiple patches to address the security and privacy issues.

Zoom agreed to pay $85 million to settle a lawsuit alleging it violated user privacy by sharing personal data with Facebook, Google, and LinkedIn, and letting hackers disrupt Zoom meetings in a practice called "Zoombombing."

### Real life example of the how perfecting before releasing results in amazing achievements

#### Apple

Apple is known for its meticulous attention to detail and focus on perfecting products before releasing them to the market.
The complexity of their products is hidden behind an intuitive user interface, which is the result of extensive testing and refinement. Apple's commitment to quality and user experience has made its products highly desirable and successful in the market. By focusing on perfection and refinement, Apple has built a loyal customer base and established itself as a leader in the tech industry. Apple's success demonstrates the value of perfecting products before releasing them to ensure a positive user experience and long-term success.

#### Google

Google is another company that emphasizes perfection and continuous improvement in its products and services. Google's search engine, for example, undergoes constant updates and refinements to deliver accurate and relevant search results to users. Google's commitment to quality and innovation has made it the most popular search engine in the world. By focusing on perfection and continuous improvement, Google has maintained its position as a leader in the tech industry and a trusted source of information for users worldwide.

Google is a prime example of a company that effectively uses feature toggles to manage and deploy new features across its wide range of complex products and services.
Google's products, such as Gmail, Google Maps, and Google Search, are continuously updated with new features and improvements. To ensure a seamless user experience and minimize disruptions, Google uses feature toggles to enable or disable new features based on user feedback, testing results, and performance metrics.

#### Facebook

Even though Zuck is known for the motto "Better done than perfect", Facebook was not released to everyone at once. It was first released to Harvard students, then Ivy League students, then US colleges, then the world. This allowed Facebook to perfect the product before releasing it to the world.

Facebook is another company that leverages feature toggles to manage its platform's features and functionalities. The social media giant has a very vast and complex ecosystem with lots of features and functionalities.
Facebook's extensive user base and complex ecosystem require careful planning and testing of new features before full deployment. Feature toggles allow Facebook to roll out new features gradually, monitor their performance, and make adjustments based on user feedback. This approach helps Facebook maintain a stable platform while continuously innovating and improving the user experience.

#### Sea of Thieves

Sea of Thieves is a popular multiplayer pirate adventure game developed by Rare. It took Rare 4 years to develop the game before releasing it to the public. The game was first announced at E3 2015 and released in March 2018. The game was developed with a focus on quality and user experience, with extensive testing and refinement to ensure a smooth and enjoyable gaming experience. The team allowed fans to take part in the game's development by joining the Insider's Program, which granted players access to an early build of the game. The program allowed Rare to experiment with different features while collecting players' feedback. The participants could also discuss with the developers in a private forum.[36] More than 30,000 players joined the program. Through the program, Rare learned more about how players interact with each other and used the information to help the team make gameplay decisions By perfecting the game before release, Rare was able to build a dedicated player base and maintain a vibrant community around Sea of Thieves. The game's success demonstrates the value of perfecting products before releasing them to the public.

Rare, uses feature toggles to manage its content updates and gameplay changes. The game's developers regularly release new content, events, and features to keep players engaged. Feature toggles allow Rare to enable or disable new content based on player feedback, ensuring a smooth and enjoyable gaming experience. By using feature toggles, Sea of Thieves can test new features, gather player data, and make informed decisions about future updates. This approach helps the game maintain a dedicated player base and a vibrant community more than 6 years after its initial release.

## ~Fail Fast~

In theory, failing fast allows you to quickly identify and fix issues.

In practice, failing fast is dangerous because starting over multiple times is often more resource expensive than handling the error and continuing execution.

### Recover quickly.

Develop mechanisms of control.

Crashing an airplane won't teach you as much as using a wind tunnel to fly a model in an environment that you can control.

Instead of returning immediately a single error, make an observable arrays of reasons to abort so that you can solve all at once instead of one by one after restarting multiple times.

### For example

Let's say you want to validate that a user can submit a login form.

Fail fast would require you to write a function like that:

```js
const canSubmit = function (email, password) {
  if (!email) {
    return false;
  }
  if (!password) {
    return false;
  }
  return true;
};
```

Instead, it should be written this way:

```ts
const reasonsToDisableSubmitButton = function (email, password): string[] {
  let reasons = [];
  if (!email) {
    reasons.push("missing email");
  }
  if (!password) {
    reasons.push("missing password");
  }
  if (password.length < 8) {
    reasons.push("password too short");
  }
  if (password === "123456789") {
    reasons.push("password too easy");
  }
  return reasons;
};

const canSubmit = function (email, password) {
  const reasons = reasonsToDisableSubmitButton(email, password);
  if (reasons.length > 0) {
    return false;
  }
  return true;
};
```

### Real life example of the disastrous consequences of following the fail fast principle

#### Boeing 737 MAX 2019 groundings

The Boeing 737 MAX is an American narrow-body aircraft series designed and produced by Boeing Commercial Airplanes as the fourth generation of the Boeing 737, succeeding the Boeing 737 Next Generation (NG).

In March 2019, the Boeing 737 MAX was grounded worldwide following two fatal crashes. The U.S. Federal Aviation Administration (FAA) and Boeing identified the cause as a software problem, leading to the Maneuvering Characteristics Augmentation System (MCAS) flight control feature being activated in response to erroneous angle of attack (AoA) information.

On November 18, 2020, the FAA rescinded the order that grounded the 737 MAX, and the aircraft returned to commercial service on December 9, 2020, with a flight by American Airlines.

It is estimated that the grounding of the 737 MAX cost Boeing $20 billion.

Fail fast is a principle that was applied to the development of the 737 MAX.

It lead to the development of a system that was not resilient to failure and that was not able to recover from it. The result was a system that was not safe and that costed Boeing $20 billion.

The principle of failing fast is not the only reason why the 737 MAX failed but it is one of the reasons.

### Real life example of the how recovering quickly results in amazing achievements

#### SpaceX

Jarrett Farnitano is a software engineer at SpaceX, where he works on the Dragon spacecraft's software. He has shared insights into SpaceX's approach to software development, emphasizing the importance of recovering quickly from failures. "It is important in safety critical software that if a single software component were to have a problem, it does not impact the entire software system. Software also often depends on the hardware it is interacting with, so must account for hardware failures as well. Crashing and restarting just isn't an option. We approach this by building the software in modular components, writing defensive logic, and checking the status of each operation. If an operation we expect to complete fails, we have defined error handling paths and recovery strategies. Sometimes that strategy just means skipping over the operation. Sometimes the strategies can be more complex and involve responses such as switching to backup systems."

#### Netflix

Netflix uses a similar approach to software development, focusing on resilience and fault tolerance. The company's Chaos Engineering team is responsible for testing the system's ability to recover from failures. By intentionally introducing failures into the system, Netflix can identify weaknesses and improve its resilience. This approach allows Netflix to recover quickly and maintain a high level of service availability for its users.

## ~Don't Repeat yourself (DRY)~

In theory it's better to have a single source of truth to avoid inconsistencies.

In practice a single source of truth makes it harder to maintain and evolve a system because if two things look the same today it doesn't mean they will look the same tomorrow.

Most likely they will diverge in upcoming versions.

### Repeat yourself.

WET: Write everything twice

Generalize only after a threshold of repetition.

Duplications are less costly to modify and adjust than abstractions and there is never enough granularity.

Use comments to lists places where similar code is in use and attach an identifier to make it easier to search for duplicates.

Use global search to find all the places where something is used, use regex to be more precise and effective in your search.

### For example

Let's consider a scenario where you're developing a web application that allows users to calculate the area of different shapes.

You might be tempted to write a single function to calculate the area of all shapes:

```js
function calculateArea(shape, width, height) {
  if (shape === "rectangle") {
    return width * height;
  } else if (shape === "square") {
    return width * width;
  } else if (shape === "circle") {
    return Math.PI * width * width;
  } else if (shape === "triangle") {
    return 0.5 * width * height;
  } else {
    throw new Error("Unsupported shape");
  }
}
```

The issue with this is that it violates the Single Responsibility Principle (SRP). The function is responsible for calculating the area of all shapes, which means it has multiple reasons to change. If a new shape is added, the function needs to be updated to include the new shape. If the calculation logic for a shape changes, the function needs to be updated to reflect the new logic. This makes the function more complex and harder to maintain.

Let's consider an alternative approach where we write a separate function for each shape to follow the WET principle

```js
// Functions to calculate the area for different shapes
function calculateRectangleArea(width, height) {
  return width * height;
}

function calculateSquareArea(width) {
  return width * width;
}

function calculateCircleArea(radius) {
  return Math.PI * radius * radius;
}

function calculateTriangleArea(base, height) {
  return 0.5 * base * height;
}

const shapeCalculations = {
  rectangle: calculateRectangleArea,
  square: calculateSquareArea,
  circle: calculateCircleArea,
  triangle: calculateTriangleArea,
};

const isFunctionDefined = function (func) {
  return typeof func === "function";
};

const featureFlags = {
  rectangle: true,
  square: true,
  circle: false,
  triangle: true,
};

const canCalculateArea = function (shape) {
  const reasons = [];

  if (!(shape in featureFlags))
    reasons.push(`Calculation for ${shape} is not supported`);
  if (featureFlags[shape] === false)
    reasons.push(`Calculation for ${shape} is disabled`);

  if (featureFlags[shape] && !isFunctionDefined(shapeCalculations[shape])) {
    reasons.push(`Calculation function for ${shape} is not defined`);
  }

  return { canCalculate: reasons.length === 0, reasons };
};

function calculateArea(shape, ...args) {
  const calculationFeasibility = canCalculateArea(shape);

  if (calculationFeasibility.canCalculate) {
    const calculationFunction = shapeCalculations[shape];
    return calculationFunction(...args);
  }

  throw new Error(calculationFeasibility.reasons.join("\n"));
}
```

### Real life example of the disastrous consequences of following the don't repeat yourself principle

#### Knight Capital Group incident (2012)

On August 1, 2012, Knight Capital Group, a high-frequency trading firm, experienced a software error that caused it to lose $440 million in just 45 minutes. The error was caused by a faulty deployment: Not all servers were updated at the same time, which led to a mismatch between the old and new code. This mismatch caused the system to place erroneous orders, which resulted in massive losses for the company.

The incident also led to a significant drop in the company's stock price, which resulted in a loss of over $10 billion in market value.
The company was forced to sell itself to a competitor to avoid bankruptcy.

The Knight Capital incident is a prime example of the dangers of the DRY principle.

The company's developers were trying to avoid duplication by replacing old code with new code.

If they had followed the WET principle the old code would have been left in place and the new code would have been added in a separate location.

This would have allowed the company to continue operating while the new code was being tested. If the new code had been found to be faulty, the company could have reverted to the old code without any issues. Instead, the faulty deployment caused massive losses and ultimately led to the company's demise.

It was not the only reason why the company failed but it is one of the reasons.

#### Patriot Missile Failure (1991)

During the Gulf War in 1991, a Patriot missile defense system failed to intercept an incoming Scud missile, resulting in the deaths of 28 American soldiers and injuries to over 100 others. The failure was attributed to a software bug that caused the system's clock to drift over time, leading to inaccuracies in tracking the Scud missile's position. The tracking error came from two different versions on internal clocking routing; one was from older missile system (from assembly code), another was an updated routing for newer faster missiles.
The mismatch created a time skew large enough to allow the Scud to be ½ kilometer off its computed location.
This shows how not repeating yourself can lead to catastrophic consequences.

#### Ariane flight V88 (1996) Code Reuse

The Ariane 5 rocket failure in 1996 was attributed to a software error. The rocket swerved off course and exploded 40 seconds after liftoff due to an unhandled overflow/carryover during a 64-to-16-bit floating point to signed integer conversion. The module responsible for the exception was redundant at the time of the crash, and its function was related to alignment before lift-off, required to run for some time after lift-off with the previous version, Ariane 4. The code was reused from the Ariane 4 version and it resulted in a genuine disaster.

It was not the only reason why the rocket failed but it is one of the reasons. See also: [Ariane flight V88 (1996) Requirements Error](10-Popular-Programming-Principles-DEBUNKED.md#ariane-flight-v88-1996-requirements-error)

### Real life example of the how WET results in amazing achievements

#### Google

Google's software development processes often involve continuous integration and deployment, where new code is tested separately before being rolled out. This approach allows Google to maintain stable operations while introducing new features or updates. Google's uptime and reliability are critical for its services, such as search, email, and cloud computing, which millions of users rely on daily.

#### Facebook

Facebook also employs a similar approach to Google, utilizing continuous integration and deployment to test and roll out new code separately. This helps them avoid major disruptions to their platform while ensuring that updates are thoroughly tested before reaching users. Facebook's commitment to stability and reliability is essential for maintaining user trust and engagement across its various products and services.

#### Amazon

Amazon's extensive use of microservices architecture enables them to deploy new code independently for different parts of their platform. This allows them to update and test new features or improvements without affecting the entire system. Amazon's focus on modularity and scalability helps them maintain a high level of service availability and performance for their e-commerce, cloud computing, and other services.

#### Netflix

Netflix is known for its sophisticated approach to software development, which includes extensive testing and continuous deployment practices. By following the WET principle, Netflix can introduce new features or fixes while minimizing the risk of disruptions to its streaming service. Netflix's commitment to reliability and performance is crucial for delivering a seamless viewing experience to its global audience.

These companies prioritize stability and reliability in their software development processes by following practices that allow them to write new code separately from existing systems, reducing the likelihood of catastrophic errors

#### Uber

Uber minimizes disruptions to its service by using feature flags and gradual rollouts to introduce new features or updates. This approach allows Uber to test new code in a controlled environment before deploying it to all users. By following the WET principle, Uber can maintain a high level of service availability and reliability for its ride-sharing platform.

#### Dropbox

Dropbox, a file hosting service, embraces continuous deployment practices to deliver a reliable and secure cloud storage solution to its users. By writing new code separately and testing it rigorously, Dropbox can introduce new features and updates seamlessly while ensuring data integrity and privacy. Dropbox's commitment to stability and performance is essential for maintaining user trust and loyalty.

## ~You Ain't Gonna Need It (YAGNI)~

In theory, it's better to avoid over-engineering and only implement what's needed.

In practice, it's better to prepare the system for what's required to avoid accumulating defects which will inevitably lead to some kind of failure.

Even though YAGNI was coined by Ron Jeffries, a software engineer, it was never intended to be an engineering principle but a procurement principle. (see also: [10 Popular Purchasing principles DEBUNKED](10-Popular-Purchasing-Principles-DEBUNKED.md#be-skeptical))

### You will probably need this.

Recognize that Mistakes happen but also that Failure is not an option.

Make sure that if there are defects, they have a workaround and they are in secondary features.

Classify defects severity with "has_no_workaround" and "is_critical_component" flags.

The more flags checked, the more severe the defect.

You can evaluate the criticality of a component based on how much other components rely on it to function properly.

You can evaluate whether there is a workaround by looking at what other components could perform the same functionality.

### For example

Let's make an analogy with the human body.

The heart is a critical component because many organs directly relying on the hearts functions:

- The brain, requires a constant supply of oxygen and nutrients carried by blood
- The kidneys, proper blood flow is necessary for their filtration process
- The liver, relies on a steady supply of oxygenated blood to digest
- The lungs, require a good blood supply to sustain their own cellular functions
- The muscles, require oxygen and nutrients to function during activities
- The heart itself, the heart also needs a steady supply of oxygenated blood. Coronary arteries supply the heart muscle with the oxygen and nutrients necessary for its own metabolic processes.

The index finger, while important for dexterity and fine motor skills, has some redundancy or workarounds:

- Adjacent fingers: Other fingers can compensate for the loss of the index finger to a certain extent. Tasks like gripping, pointing, or picking up objects can still be accomplished, albeit with some difficulty.
- Adaptation of Hand Movement: With practice and adaptation, individuals can learn to use different hand movements or techniques to perform tasks that primarily involve the index finger. They might adjust their grip or use alternative methods.
- Tools and Aids: Depending on the task, various tools or aids can substitute for the index finger. For instance, using a stylus or certain types of grips for writing, typing, or handling objects can mitigate the absence of the index finger.
- Rehabilitation and Prosthetics: Advances in medical technology provide prosthetic options or rehabilitation methods that can partially restore the functionality of the index finger. Prosthetics and rehabilitation therapy can help individuals regain some dexterity and movement.

### Real life example of the disastrous consequences of following the YAGNI principle

#### Ariane flight V88 (1996) Requirements Error

The Ariane 5 rocket failure in 1996 was attributed to a software error.

The rocket swerved off course and exploded 40 seconds after liftoff due to an unhandled overflow/carryover during a 64-to-16-bit floating point to signed integer conversion.

The module responsible for the exception was redundant at the time of the crash, and its function was related to alignment before lift-off, required to run for some time after lift-off with the previous version, Ariane 4.

The oversights in the software resulted in a genuine disaster. The possibility of this Operand Error had been considered, but due to maximum workload constraints, protection was only applied to four of seven variables, despite the fact that analyses showed that this particular conversion could throw an Operand Exception.

This is most likely due to the system constraints, in addition to a combination of reasonably high certainty that this error would not occur.

The failure was a result of a tragic lack of humility and a requirements error.

Had they not followed the YAGNI principle, they would have been able to prepare the system for what was required and avoid the failure.

It caused a loss of around $370 million and a reputation loss for the European Space Agency and the French space program.

It was not the only reason why the rocket failed but it is one of the reasons.

#### Chrysler Comprehensive Compensation System

The Chrysler Comprehensive Compensation System (C3) was a payroll system that was supposed to replace the old payroll system that was composed of 5 different systems.

It was never able to replace the old system because it was missing features that were required by the users and it was not able to handle the load of the old system.

The software engineering team worked for 7 years and although they achieved some technical goals they never managed to deliver a working payroll system. The project was eventually cancelled. The so called customer representative resigned due to burnout and stress, and could not be replaced.

## ~Read the fucking manual (RTFM)~

In theory, the manual contains all the information needed to use the system effectively and efficiently. It should be the primary source of information for users.

In practice, manuals are often out of date, difficult to understand, and don't provide enough details to fully understand how the system works. Relying solely on the manual can lead to confusion and frustration.

### Don't rely on a manual.

Make assertions to probe the system.

Help project maintainers make their code more intuitive by comparing how you expect the system to work and how it is actually working.

### For example

Let's consider the documentation for a widely-used open-source project, like Git, the version control system. Over time, Git has had comprehensive documentation, but it's a complex tool that undergoes updates and changes. As a result, some aspects of the documentation might not always perfectly align with the latest version or might lack details on newer functionalities.

For instance, imagine a scenario where the Git documentation hasn't been updated to include a newly introduced command that simplifies the process of reverting changes within a repository. The manual might still suggest a more convoluted approach that was standard before the introduction of this newer, more efficient command.

In such a case, relying solely on the manual might lead users to follow outdated or less efficient procedures. However, proactive exploration and testing within the Git system could reveal this new command and its functionalities. Users who delve into the system and compare their expectations of functionality based on the manual with the actual capabilities of the updated Git version might notice discrepancies.

These users could then contribute by informing the maintainers about the missing or outdated information in the documentation. By doing so, they help the maintainers update the manual, ensuring that it accurately reflects the current features and capabilities of the Git system. This, in turn, assists other users who rely on the documentation to utilize the latest and most efficient tools available within Git.

### Real life example of the disastrous consequences of following the RTFM principle

#### Mars Climate Orbiter failure

Consider the case of the Mars Climate Orbiter mission in 1999. The mission aimed to study the Martian climate, but unfortunately, it ended in failure due to a navigation error.

The spacecraft was equipped with thrusters for course corrections. However, there was a critical issue in the navigation system that led to the spacecraft getting too close to Mars during its orbital insertion. The problem originated from a mix-up in units: one part of the team used imperial units (pound-seconds) for thruster calculations, while another part used metric units (newton-seconds) in the navigation software.

The discrepancy between these measurement units led to miscalculations in the spacecraft's trajectory. As a result, the spacecraft came too close to Mars and entered the planet's atmosphere, ultimately disintegrating due to the extreme heat and forces.

The mission's failure stemmed from a communication breakdown between different teams and contractors, that both reliance on assumed standards. The information provided in the manuals and documentation didn't highlight the importance of unit consistency across different parts of the mission, leading to catastrophic consequences.

This event underscores the significance of meticulous cross-verification of systems, and an understanding beyond what the manual explicitly covers.

Had they not followed the RTFM principle, they would have focused on writing assertions to probe the system and would have been able to avoid the failure.

It caused a loss of around $193.1 million and a reputation loss for NASA.

## ~Maintain UI consistency~

In theory, UI consistency makes it easier for users to navigate and interact with the interface.

In practice, Trying to maintain UI consistency over time is a fool's errand because it's impossible to predict how the UI will evolve.

### Focus on the user experience and functional requirements.

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

### Real life example of the disastrous consequences of following the maintain UI consistency principle

#### Windows 8

One notable real-life example of the disastrous consequences of strictly adhering to UI consistency principles occurred with the launch of Microsoft's Windows 8 operating system in 2012.

Traditionally, Windows operating systems maintained a consistent _user experience_ across versions, making it easier for users to transition between updates.

However, with Windows 8, Microsoft introduced a radical departure from the familiar Start menu interface, replacing it with the tile-based "Metro" interface. This move aimed to create a unified UI across desktops, laptops, and touch-based devices.

It was a significant change that required users to relearn how to navigate the operating system.

The new interface was not well-received by users, who found it confusing and difficult to use.

As a result, Windows 8 was a commercial failure.

It was such a failure that Microsoft skipped Windows 9 and had to release a new version, Windows 10, to address the issues.

The failure of Windows 8 and the Surface RT led to a significant financial impact for Microsoft. The company took a $900 million charge for its inventory of unsold Surface tablets, which was attributed to the slow sales of the Surface RT and the confusion surrounding its Windows RT operating system.
This inventory write-down resulted in a substantial selloff of Microsoft shares and wiped out $34 billion in market value
While the exact cost of the Windows 8 UI failure is not explicitly mentioned, the $900 million write-down provides a clear indication of the financial impact associated with the unsold inventory of Surface tablets, which was a result of the Windows 8 and Surface RT underperformance.

### Real life example of the how focusing on UX results in amazing achievements

#### Craigslist

Craigslist is a prime example of a successful platform that prioritizes user experience over UI consistency.

Craigslist's interface has remained largely unchanged since its inception in 1995, with a simple, text-based design that focuses on functionality over aesthetics. The platform's primary goal is to connect users with local services, goods, and job listings in a straightforward and efficient manner. While the design may appear outdated compared to modern websites, Craigslist's focus on usability and functionality has contributed to its enduring popularity. The platform's minimalist approach and emphasis on user experience have made it a go-to destination for classified ads and community engagement. Craigslist's success demonstrates that prioritizing user experience can lead to long-term success, even if it means sacrificing UI consistency.

#### Steam (Valve Corporation)

Steam, the digital distribution platform developed by Valve Corporation, is another example of a successful platform that prioritizes user experience over UI consistency. Steam's interface has evolved over the years to accommodate new features and services, but the platform's focus on usability and functionality remains consistent. Steam's user-friendly design allows gamers to browse, purchase, and play games seamlessly, with features like cloud saves, automatic updates, and community forums enhancing the overall gaming experience. While Steam's interface may not adhere strictly to UI consistency principles, its emphasis on user experience has made it a leading platform in the gaming industry. Steam's success highlights the importance of prioritizing user experience to create a positive and engaging platform for users.

They own about 50% of the digital distribution market for video games.

## ~Be conservative in what you send, be liberal in what you accept (Postel's Law)~

In theory, it's better to be flexible and lenient when receiving data to avoid breaking the system when receiving unexpected data or data that doesn't conform to the expected format or structure.

In practice, malicious actors exploit lax input validation to inject harmful code or manipulate protocols, leading to security vulnerabilities and data breaches that can have serious consequences.

### Be conservative in both what you send and receive.

Strict input and output validation improves interoperability by enforcing clear communication standards.

Sanitize data, Parameterize queries, use whitelists.

### For example

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

### Real life example of the disastrous consequences of following Postel's Law

#### Equifax data breach

One classic example that illustrates the repercussions of lax input validation leading to a significant security breach is the Equifax data breach in 2017. Equifax, one of the largest consumer credit reporting agencies, experienced a massive breach that exposed sensitive personal information of over 147 million individuals.

The breach was caused by a vulnerability in the Apache Struts web application framework, which was used by Equifax to build its online dispute portal. The vulnerability allowed attackers to inject malicious code into the portal, which led to the exposure of sensitive data.

The vulnerability was caused by a lack of input validation and sanitization. The portal accepted user input without proper validation, which allowed attackers to inject malicious code into the system. This code was then executed on the server, leading to the data breach.

The company's stock price dropped by 33% in the days following the breach, and it was forced to pay $700 million in fines and penalties.
In total, the breach cost Equifax over $1.4 billion.

## ~It always takes longer than you expect (Hofstadter’s Law).~

In theory, estimating the time required to deliver a project will always be inaccurate because there are too many unknowns and uncertainties to account for in advance, this leads to people making top down estimates that are not actionable and therefore useless.

In practice, It's possible to make increasingly more accurate estimates by breaking down the project into smaller components and estimating the time required for each component individually before adding them up to get an overall estimate for the project as a whole (bottom-up estimation).

### Make a Work Breakdown Structure (WBS).

Breakdown a project into components and sub-components.

Try to break down into 7 sub-components at most because it's the average maximum number of things a human can keep in mind at once.

Refine your estimates as you refine your specifications by sizing your pessimism.

Each deepest sub-component break it down into 3 parts:

- the optimistic duration, the duration it will take to make if everything goes smoothly, no mistakes, no uncertainties
- the buffer for realistic duration, the additional duration it will take to fix eventual mistakes (skill issues)
- the buffer for pessimistic duration, the additional duration caused by uncertainty and lack of clarity in specifications (domain knowledge issues)

By sizing your degree of pessimism and therefore uncertainty for each deliverable you will be able to tell whether more work should be done on the specifications and preliminary work to reduce this pessimism.

### For Example

#### Estimates

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

#### Program management

```
  - [ ] Project A
    - [ ] Feature AA
      - [ ] Component AAA
        - [ ] Functionality AAAA Allows users to do something by doing something
        - [ ] Functionality AAAB Allows users to do something by doing something
      - [ ] Component AAB
    - [ ] Feature AB
      - [ ] Component ABA
      - [ ] Component ABB
      - [ ] Component ABC

```

In this example we can see that sometimes the pessimistic buffer is even larger than the realistic buffer. This sub-component should be investigated for potential specifications improvements.

If the clarification of the specifications takes longer than the pessimistic buffer, maybe it's not worth it to clarify and just go with common sense.

### Real life example of the how bottom up estimation results in amazing achievements

#### Apollo program

The Apollo program, conducted by NASA during the 1960s and early 1970s, stands as one of the most ambitious and successful examples of bottom-up estimation resulting in remarkable achievements.

The goal of the Apollo program was announced by President John F. Kennedy in 1961, who declared that the United States would commit to a manned lunar landing and return mission. The program aimed to land humans on the Moon and safely return them to Earth before the end of the decade.

Achieving this feat required meticulous planning, engineering, and estimation across numerous components and stages of the mission.

The Apollo program was divided into three phases: Earth orbit, lunar orbit, and lunar landing. Each phase had its own set of objectives and requirements, which were broken down into smaller components and sub-components.

The program costed $25.4 billion in 1973, but the investment paid off with the successful landing of Apollo 11 on July 20, 1969 and the safe return of the crew to Earth.

Many of the techniques and technologies developed during the Apollo program are still in use today in everyday life.

Among others: the GPS, artificial limbs, water purification systems, computer microchips, wireless headsets, scratch-resistant lenses and many more.

It is estimated that the space program generated $7–$14 in economic return for every dollar invested.

#### The Channel Tunnel

The Channel Tunnel is a 50.45-kilometre (31.35 mi) railway tunnel that connects Folkestone (Kent, England, UK) with Coquelles (Hauts-de-France, France) beneath the English Channel at the Strait of Dover.

It is the only fixed link between the island of Great Britain and the European mainland.

At its lowest point, it is 75 m (250 ft) deep below the sea bed and 115 m (380 ft) below sea level.

The Channel Tunnel was built between 1988 and 1994, and cost £4.65 billion ($7.5 billion) to construct.

It was a remarkable achievement in engineering, and it stands as one of the most ambitious and successful examples of bottom-up estimation resulting in remarkable achievements.

The project was divided into three phases: design, construction, and operation. Each phase had its own set of objectives and requirements, which were broken down into smaller components and sub-components.

The project was completed on time and within budget, and it has been in operation since 1994.

The Channel Tunnel is a testament to the power of bottom-up estimation and planning.

#### The Millau Viaduct

The Millau Viaduct is a cable-stayed bridge that spans the valley of the River Tarn near Millau in southern France. It is the tallest bridge in the world, with one mast's summit at 343.0 metres (1,125 ft) above the base of the structure. It is the 12th highest bridge deck in the world, being 270 metres (890 ft) between the road deck and the ground below.

The Millau Viaduct was built between 2001 and 2004, and cost €394 million ($524 million) to construct.

It was completed on time and it has been in operation since 2004.

A WBS was used to break down the project into smaller components and sub-components.

## ~Premature Optimization is the root of all evil (Donald Knuth)~

In theory, optimization in the early stages of development is unnecessary and can lead to wasted time and effort.

In practice, delaying optimization until later stages will lead to significant performance issues that are costly to rectify and will lead to product market fit failure.

### Make fast benchmarking part of your development process.

Focus your optimization efforts on high level evaluations and long term functional requirements (LFRs).

Look at the overall process before going into details.

Make use of a variety of test:

- speed tests, short time to execute critical operations
- load tests, fast responses to different levels of activity
- scalability tests, low resource utilization as activity grows
- stress tests, high stability as we get closer to the edge
- reliability tests, high consistency in error handling over time

Characteristics of long-term functional requirements (LFRs):

- Core functionality, capable of addressing the needs of the company to deliver the unique value proposition, for example supporting sales, marketing, product delivery
- Durable and scalable, capable of withstanding a growing demand, for example supporting multiple languages, devices, currencies
- Aligned with the product vision, capable of placing the company as the leader of the market, for example supporting de facto standards and becoming a de facto standard

Performance optimization should be part of the development process from the start and sometimes even part of the product (Google displays how many results it found in a fraction of a seconds).

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

### Real life example of the disastrous consequences of following the principles saying that premature optimization is the root of all evil

#### Cyberpunk 2077 launch

One notable example is the launch of Cyberpunk 2077 by CD Projekt.

Cyberpunk 2077 was highly anticipated and promised to be a groundbreaking game with a vast open world and cutting-edge graphics.

The developers, CD Projekt, faced immense pressure to deliver a feature-rich and visually stunning experience.

However, in their pursuit of meeting ambitious deadlines and delivering on promised features, they reportedly neglected optimization during the early stages of development.

The consequence of this decision became apparent upon the game's release in December 2020.

Cyberpunk 2077 encountered widespread criticism for its poor performance, especially on last-generation consoles like PlayStation 4 and Xbox One.

Players experienced numerous bugs, crashes, and subpar frame rates, significantly impacting the overall gaming experience.

CD Projekt Red had to issue public apologies and commit to releasing multiple patches to address the performance issues.

The lack of early optimization not only tarnished the game's reputation but also led to financial repercussions for the company, as refunds were offered to dissatisfied customers.

CD Projekt Red lost a significant amount of revenue when Cyberpunk 2077 was removed from the PlayStation Store.

The company's stock value dropped by 75%, from around zł400 ($85) a share on the Warsaw Stock Exchange to zł93.81 ($19.92) just before the game's release.

The exact financial loss from being removed from the PlayStation Store is not publicly available, but the overall impact on the company's stock value and reputation was substantial.

The company also faced a lawsuit from its investors and was required to pay a settlement of $1.85 million.

#### Healthcare.gov launch

Another notable example of lack of early optimization leading to disastrous consequences is the launch of the Healthcare.gov website in 2013.

The website was created to allow Americans to sign up for health insurance under the Affordable Care Act (ACA).

However, the website experienced numerous technical issues, including slow loading times and frequent crashes.

The website was not optimized for performance, leading to poor user experience and low adoption rates.

The website was eventually fixed, but the initial problems caused significant delays in the rollout of the ACA.

Bloomberg News reported the cost exceeded $2 billion.

Performance was not the only reason why the website failed but it is one of the reasons. It was a major factor in the delay of the rollout of the ACA.

## ~The less it knows the better (Law of Demeter)~

In theory, the Law of Demeter (LoD) states that a module should have have limited knowledge of other modules to avoid tight coupling and minimize dependencies.

In practice, following LoD leads to significant performance and maintainability issues because it requires writing wrappers to satisfy it.

### Create a single entry point

Prefer the Facade pattern which provides a cleaner, more intuitive interface to interact with complex systems, ultimately improving both performance and maintainability of the codebase.

### For example

The facade pattern in Node.js can be used to simplify interactions with complex systems or libraries by providing a simplified interface.

Suppose you have a complex module that interacts with a database. This module has various functions to perform database operations:

```javascript
// Complex module interacting with the database
class Database {
  connect() {
    // Code to establish a database connection
    console.log("Connecting to database...");
  }

  query(sqlQuery) {
    // Code to perform a database query
    console.log(`Executing query: ${sqlQuery}`);
    // Execute the query and return results
    return `Results for query: ${sqlQuery}`;
  }

  disconnect() {
    // Code to close the database connection
    console.log("Disconnecting from database...");
  }
}
```

Now, let's create a facade for this `Database` class to simplify its usage:

```javascript
// Facade for interacting with the database
class DatabaseFacade {
  constructor() {
    this.database = new Database();
    this.database.connect();
  }

  runQuery(sqlQuery) {
    return this.database.query(sqlQuery);
  }

  closeConnection() {
    this.database.disconnect();
  }
}
```

In this example, `DatabaseFacade` acts as a simplified interface for interacting with the complex `Database` class. Instead of directly using the `Database` class and dealing with its methods, developers can use the `DatabaseFacade` class, which provides a more straightforward and limited set of methods.

Usage example:

```javascript
// Using the facade pattern to interact with the database
const dbFacade = new DatabaseFacade();
const result = dbFacade.runQuery("SELECT * FROM users");
console.log(result);
dbFacade.closeConnection();
```

This usage demonstrates how the facade pattern encapsulates the complexity of the `Database` class, allowing users to interact with it using a simpler interface (`DatabaseFacade`) without needing to understand the inner workings of the underlying `Database` class.

### Real life examples of how creating a single entry point leads to amazing achievements

#### Linux kernel

One notable example of how creating a single entry point leads to amazing achievements is the development of the Linux kernel.

The Linux kernel is the core component of the Linux operating system, which is used in a wide range of devices, from smartphones to supercomputers.

The kernel is responsible for managing the system's resources and providing an interface for user applications to interact with the hardware.

The Linux kernel is a complex system with numerous components and functionalities. However, it provides a single entry point for user applications to interact with the system: the system call interface. This interface allows user applications to request services from the kernel, such as file operations, process management, and memory management. The kernel then handles these requests and returns the results to the user application.

By providing a single entry point, the Linux kernel simplifies the interaction between user applications and the system. This makes it easier for developers to build applications on top of the kernel and improves the overall performance and maintainability of the system. It also allows the kernel to evolve independently from user applications, which can be updated without affecting the kernel. This decoupling of the kernel from user applications is a key factor in the success of Linux as an operating system. It allows the kernel to be used in a wide range of devices and applications, from smartphones to supercomputers.

It is estimated that the Linux kernel is used in over 90% of the world's supercomputers and 82% of the world's smartphones.

Another notable example of how creating a single entry point leads to amazing achievements is the development of the World Wide Web.

#### World Wide Web

The World Wide Web is a global system of interconnected computer networks that use the Internet protocol suite (TCP/IP) to link devices worldwide.

The Web was developed in the late 1980s and early 1990s by Tim Berners-Lee at CERN, a European research organization.

The Web was initially conceived as a way to share information between researchers at CERN and other institutions. However, it quickly evolved into a global system that allowed anyone to publish and access information on the Internet.

The Web is built on top of the Internet, which provides the underlying infrastructure for data transmission. However, the Web provides a single entry point for users to access information on the Internet: the Uniform Resource Locator (URL). This allows users to access any resource on the Internet by specifying its URL, which consists of a protocol identifier followed by the resource's location.

By providing a single entry point, the Web simplifies the process of accessing information on the Internet. This makes it easier for users to find and access the information they need, which has led to the Web becoming the most popular way of accessing information on the Internet.

It is estimated that there are over 1.8 billion websites on the Internet, with over 4.5 billion Internet users worldwide.

#### AWS API Gateway

Another notable example of how creating a single entry point leads to amazing achievements is the AWS API Gateway.

The AWS API Gateway is a service that allows developers to create, publish, maintain, and monitor APIs for their applications.

The API Gateway provides a single entry point for developers to access the functionality of their applications. This makes it easier for developers to build applications on top of the API Gateway and improves the overall performance and maintainability of the system.

It is estimated that the AWS API Gateway is used by over 1 million developers worldwide.
