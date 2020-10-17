# Introduction to Quantum informatics
In this course we will discuss the more interesting parts of quantum informatics

## Prerequisites
- Linear algebra(and maybe a little geometry)
- A little combinatorics

## Quantum properties, events and sets
Up until the 20th century, a physics system could be described by Ω(a set of all possible states)

## Некомутативност на събитията
( ще го преведа, когато намеря подходящ термин на английски )

С прости думи **има** значение кое събитие ще се случи първо

```
p(A) . p(B|A) =/= p(B) . p(A|B) <- A contradiction to the Bayes's law
Where: (and everywhere else I use them for that matter)
- p(A), p(B)  - probability of event A, or respectively B, happening
- p(A & B)    - probability of A **AND** B happening
- p(B|A)      - probability of B happening **provided** A (conditional probability)
```

## Experiment with *crossed polarizers*
- Done with photons
- Every photon can be described by an ordered triplet in the form **[** *direction*, *energy*, *inner state* **]**
- The inner state is described by the polarization of the photon(or in qunatum systems commonly called a **qu**antum **bit** -> **qubit** for short)
- The used photons are linearly polarized
  - meaning the polarization can be described as a line perpendicular(`_|_`) to the *direction* of the photon
  - so for a given group of photons going in the same *direction* there is a subset that has the same linear polarization
- This 'filtering' of photons with a given polarization is done via *polarization filters*(polarizers for short)
- If we put the same oriented filter behind the first one - every photon that went through the first will go through the second, because it is guaranteed to have the same polarization.
- However, if we rotate the second filter by α degrees, then we can observe that the number of photons that do make it through the second will be cos<sup>2</sup>α of the original(that went through the first one that is)
- If we were to draw it, it would look something like this:
```
~~>             |                           ~~>                         |                        ~~>
photon      polarizer(E0)       photons with polarization E0       polarizer(Eα)     photons with polarization Eα
                                  say N photons got through                            these photons should be N * cos^2(α)
```
- This experiment equates to:
  1. Aligning all the photons to have polarization E0
  1. and then passing them through the second polarizer to filter them again
  - We don't observe anything interesting with this experiment
- However, what happens if we add a third polarizer
- The Bayes's law tells us that the order of the lens should not matter, however physical experiments prove that the order does matter
- This leads physicists to believe that measurement is an active process
  - Just like when we want to see an object, we have to shine light on it first
  - In classical physics, this is not a problem, because macro-systems are not sensitive to such small changes and are usually too small to have any significant effect on the end result
- Thus 2 quantum events are called **взаимно комутиращи**/**съвместно наблюдаеми**, when they satisfy basye's theorem

## Our disturbance to the force(Star Wars reference)
By that I mean the disturbance measure introduces to micro-systems
- There is always a minimal disturbance which is not reversible
- This disturbance is measured by the Planck constant(~6.62607004 × 10<sup>-34</sup>)

## Quantum logical operations
- They can be in a relation where
  - If A => B
- Thus all properties of a given quantum set form a partially ordered set.
  - Then if it's partially ordered there **may** be operations of conjunction and disjunction
  - Thus conjunction can be defined as the biggest element that is both element of set A and set B
  - And there are always operations of conjunction and disjunction
- Because of a proof I'm too lazy to write out: the distribution law is not correct for probability in quantum systems

## The famous double slit experiment
I won't draw it, if you want to see it, just google it. The essence is that a stream of photons is shot towards a wall with 2 slits, and the resulting pattern is observed on a wall behind the slits.

### Experiment with (theoretically) infinite detector
- The results, show us how many of the photons got through
```
N         - the total number of photon
N(A)      - number of photons that went through slit A
N(B)      - number of photons that went through slit b
N(A or B) - the number of photons that went through A or B
N(A or B) = N(A) + N(B) < N
```
Then if we get a large enough detector we will catch all N(A or B) particles

### Experiment with a smaller detector
- This is the same as the infinite detector but done with a smaller one.
- If we look at the data from this experiment and use the same notations as above but label:
```
N(A and C)          - photons that went through slit A and were registered in C(the detector)
N(B and C)          - photons that went through slit B and were registered in C(the detector)
N( (A or B) and C ) - photons that went through slit A or B and were registered in C(the detector)
```
Then we observe the interesting property that `N(A and C) + N(B and C) =/= N( (A or B) and C )`, i.e. the sum of the photons that go through the slits and are registered, does **NOT** equal the total photons registered.

### First try at interpretation
We are not dealing with particles, but waves. An interesting property of waves is that the interfere with each other. This tells us that we are observing interference pattern between 2 waves. But those are not any waves. The 2 slits are origins of spherical waves which are synced to produce the pattern we are observing.

However, this explanation is rendered  useless if we introduce 2 detectors in front of the slits(they never read simultaneously). Furthermore if we let particles one by one they are registered in only one place. After enough time they will form and interference pattern. So it all comes down to the conclusion that: `The particles do not behave like waves, the probability of seeing them in the pattern is`

## Quantum logic
The mere fact that:
```
A ∩ ( B ∪ C ) =/= (A ∩ B) ∪ ( A ∩ C)
A ∪ ( B ∩ C ) =/= (A ∪ B) ∩ ( A ∪ C)
```
This proposes that there should be a field of quantum logic with these properties and a new type of quantum calculus.

## Quantum categories
No, there are not multiple types of quantum. Category in this context is the mathematical structure.

This is the answer to the necessity to describe quantum transformations. And the question: `Can quantum transformations be irreversible, or are they by definition reversible?`

## Visual representation
- Schrödinger representation - https://en.wikipedia.org/wiki/Schr%C3%B6dinger_picture (with the added notion that there can be directed transformations, not just unidirectional)
- Heisenberg picture - https://en.wikipedia.org/wiki/Heisenberg_picture (initial values are expected to be constant under change of time, as opposed to Schrödinger's representation)

## The undeterminable nature of quantum systems
- As it was discussed above(the quantum properties and noncommutative nature of consecutive events) leads to the conclusion that all results will have probabilistic nature.
- In order to have a unified way of working we will have an axiomatic representation of classical and quantum systems. Thus the end result will have pure state, which will be stripped of all probabilistic and undeterminable properties, i.e. every even will have probability 0 or 1.
- But every quantum system has these properties and we will show that for every set of `S` of events, there exists a state `q`, in which events form `S` happen with probability 0 or 1. But for every `pure` state in `q`, there exists an event `A`, which does not commute with any of the events in `S` and `A` happens in `q` with probability =/= 0 or 1 `=>` `quantum systems are always probabilistic`.

## Quantum entanglement
This will get pretty `entangled`, pretty quickly. (I'm sorry, I had to do it)
- This phenomenon is a consequence of the `compound systems`.
- Such system is the classical representation of 2 normal bits:
  - ``{bit, bit}``, which has 4 possible states: `{0,0}, {0,1}, {1,0}, {1,1}`, or more formally written as:
  ```
  {0,1} x {0,1} = { (0,0), (0,1), (1,0), (1,1) } // cartesian product
  ```
  - But it has been show that there exist `quantum pure state` in which relations(even between individual bits) are stronger than any allowed statistical system. Thus elements in a quantum system can be interdependent(dependent on each other). There are many applications where this is expected and may be of great help, just to name a few:
    - Quantum cryptography - uses this phenomenon to develop new protocols of protected communication, in which the security of the data is guaranteed by the core principles of quantum mechanics.
    - Quantum information theory - greater archive capability, greater efficiency in data transportation(speed, lower losses)
    - Quantum calculations and algorithms - thanks to quantum entanglement new algorithms can be developed which take advantage.

## Resources
- http://theo.inrne.bas.bg/~mitov/QuantumInformation2020/QI_introductory_lecture.pdf
