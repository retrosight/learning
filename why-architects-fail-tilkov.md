# Why Architects Fail

https://speakerdeck.com/stilkov/why-architects-fail

10 Diseases You Should Know About

Stefan Tilkov, innoQ

@stilkov

## 1. Over-Generalization Drive

> Symptom: Seeing commonalities in everything and turning them into generic solutions

### Phases in a Developer's Life

#### The Enthusiastic Developer

> "This stuff is cool - let's build programs! For real people!"

```
Create Customer   Create Product   Create Order
Find Customer     Find Product     Find Order
List Customers    List Products    List Orders
Edit Customer     Edit Product     Edit Order
Delete Customer   Delete Product   Delete Order
```

Boring, boring, boring.

#### The Disillusioned Developer

> "Oh. Real people have boring problems."

#### The Enthusiastic Architect

> "Generic solutions! Cool!"

```
Create Thing
Find Thing
List Thing
Edit Thing
Delete Thing
```

#### The Disillusioned Architect

```
KISS - Keep it simple stupid
YAGNI - You aren't going to need it
Lean
Minimable viable product
Story focus
```

> When you go too far up, abstraction-wise, you run out of oxygen. Sometimes smart thinkers just don't know when to stop, and they create these absurd, all-encompassing, high-level pictures of the universe that are all good and fine, but don't actually mean anything at all. These are the people I call Architecture Astronauts. _~ [Joel Spolsky](http://www.joelonsoftware.com/articles/fog0000000018.html)_

#### The "Wise" Architect

```
Question: *
Answer:   It depends.
```

## 2. Domain Allergy

> Symptom: Treating the domain as a negligible nuisance

```
        ---------------------------
        |                         |
        |    -----------------    |
10% ----|--->| Configuration |    |
        |    -----------------    |
        |    -----------------    |
        |    |               |    |
        |    |               |    |
        |    | The           |    |<---- Application
        |    | Generic       |    |      (100%)
90% ----|--->| Thing         |    |
        |    | Machine       |    |
        |    |               |    |
        |    |               |    |
        |    -----------------    |
        |                         |
        ---------------------------
```

```
              -------  -------
Functionality | 80% |  | 20% |
              -------  -------
              |     |  |      \
              |     |  |        \
              |     |  |          \
              |     |  |            \
              |     |  |              \
              -------  -----------------
Time / Effort | 80% |  |   320%        |
              -------  -----------------
```

```
              ---------------------------
              |                         |
              |    -----------------    |
              |    | Configuration |    |
              |    -----------------    |
              |    -----------------    |
              |    |               |    |
              |    |               |    |
              |    | The           |    |<---- Customer
              |    | Generic       |    |
Developer ----|--->| Thing         |    |
              |    | Machine       |    |
              |    |               |    |
              |    |               |    |
              |    -----------------    |
              |                         |
              ---------------------------
```

The benefits of choices already made

* Microsoft .NET + Visual Studio
* Ruby on Rails
* SAP et. al.

## 3. Obsessive Specialization Disorder

> Symptom: Believing every problem to be unique, even if it's been solved 1,000 times

Task: Read a file of text, determine the _n_ most frequently used words, and print out a sorted list of those words along with their frequencies.

http://www.leancrew.com/all-this/2011/12/more-shell-less-egg/

### Donald Knuth

10-page literal Pascal program, including innovative new data structure.

### Doug McIlroy

```
tr -cs A-Za-z '\n' |
tr A-Z a-z |
sort |
uniq -c |
sort -rn |
sed ${1}q
```

> Symptom: Believing everything needs to be a perfect match to your environment to be usable.

## 4. Unhealthy Complexity Attraction

> Symptom: Being so smart you can't be bothered by simple approaches.

### Benefits of Complexity

* Challenging work
* New and interesting experience
* Self-esteem
* Community
* Barrier to entry
* Job security

## 5. Analysis Paralysis

> Symptom: Taking longer to evaluate than to actually do it

```
Vendor Selection
Week 0   |  Collect and agree on requirements
Week 8   |  Conduct market research
Week 10  |  Send out RFP to selected vendors
Week 14  |  Evaluate responses, create shortlist, start PoC
Week 20  |  Evaluate PoC results, recommend vendor X
Week 26  |  Accept your CEO picked vendor Y  
```

## 6. Innovation Addiction

aka: Phase-of-Fixation

> Symptom: Things become progressively less fun the closer you get to production

> "Mindful choice of technology gives engineering minds real freedom: the freedom to contemplate bigger questions. Technology for its own sake is snake oil." _~ [Dan McKinley](http://mcfunley.com/choose-boring-technology)_

## 7. Severe Tunneling Fixation

> Symptom: Enforcing an architectural apporach that clashes with the framework, libraries or tools you use.

> "I know what I like and I like what I know..." _~ [Genesis](https://en.wikipedia.org/wiki/I_Know_What_I_Like_(In_Your_Wardrobe))_

## 8. Asset Addiction

> Symptom: Becoming so attached to a particular tool / library / framework it becomes a fit for every problem.

> Symptom: Using a fashionable technology because it's popular (aka fallacy of argument by authority).

## 9. Exaggerated Risk Aversion

> Symptom: Sticking with horrible, horrible, HORRIBLE tools because they are there.

> Symptom: Confusing "easy" with simple, creating accidental complexity.

Rich Hickey [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy)

```
simple    easy
complex   hard
```

## 10. Impact Dissonance

> Symptom: Becoming too detached from the actual system that is being delivered.

### Related: Governance Megalomania

> Symptom: Believing everything has to be approved by you to ensure it meets architecture standards.

**What architects want to do...**

```
30%  |  Shape strategy
30%  |  Make important decisions
20%  |  Explore technologies
20%  |  Mentor developers
```

**What others think architects do...**

```
40%  |  Define annoying rules
20%  |  Slow down development
20%  |  Pick the wrong tools
20%  |  Refuse to learn from devs
```

> "Architect" is Latin for "can't code anymore." _~ [Ted Neward](http://blogs.tedneward.com)_

**What architects _actually_ do...**

```
35%  |  Try to be involved
30%  |  Act as salespeople
30%  |  Defend architecture
5%   |  Do technical stuff
```

## I don't have an answer...

...so here is one, anyway.

### An Architect's Success Formula

```
Dogma and rules          |  10%
Experience               |  20%
Pragmatism               |  20%
Flexibility              |  10%
Minimalism               |  10%
Trends and future needs  |  10%
Experiments and PoCs     |  10%
Hands-on participation   |  10%
Vendor advice            |  0%
```

