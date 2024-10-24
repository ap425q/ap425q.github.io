---
title:  "Fuzzing 101"
published: false
tag: Security
category: Exploit Development
---

This blog documents my notes and learnings from my journey to learn fuzzing.
> I will be documenting the practical implementations of fuzzing in these blogs and we will not deep dive in topics such as input generation or diffrent types of mutation. We will just discuss them breifly.
> This series of blogposts is mostly focused on x86-64 architecture and windows os, But the the techniques and methodologies can be extended to other architectures and other os.


## Vulnerablity Research Approaches

### Static/Dynamic Analysis

- Good for smaller codebases (or very specific functionality)
- Can be time consuming
- Harder to Automate

### Fuzzing

- Good for complex codebases
- Write once, run forever
- Complete understanding of the target is not necessary

## What is Fuzzing?

> The examples provided are just for understanding purposes and do not represent any real world scenario.

- Target software parses controllable input example : Files, Commandline arguments, Network packets, etc

- We create and/or mutate input and feed input to the program with the goal to find crashes.

- Loop until we find the crash.

- Lets understand this with an example :

<img src="{{ site.url }}{{ site.baseurl }}/images/syncbrs.png" alt="">

- This diagram represents a normal functionality of an application where, we have an application `SyncBreeze.exe` which has lot's of functionalites and lots of dll's loaded, In one of the dll `syncbrs.dll` we have a `ParseLoginReq` functionality which we are interested to test. Description about this function is provided in the diagram.

- This is how a normal application works where we have multiple dll's loaded which contain lot's of functions.

- Now our testing setup will look something like this. 

<img src="{{ site.url }}{{ site.baseurl }}/images/syncbrs_fuzz.png" alt="">

- We only want to test `ParseLoginReq` function , Hence we will directly loaded that specific dll which contains the function, This saves lots of time and effort.

- Here we are first loading the dll using `LoadLibrary` Api call in our `Harness.exe` which is responsible for sending repetitive input to the function.We also have the `Fuzzer.exe` which is responsible for Generating inputs,Mutating inputs and Saving Interesting inputs and it also keep tracks of the coverage.
We will talk more about these terms and how it works in detail in upcoming parts of this blog.  


## Why Fuzz ?

- Some codebases are very complex and it's not feasible to manually review for bugs.

- Quicker and easier to write a fuzzer targeting specific functions and run it continously.

## What a Fuzzer does ?

- Handling Inputs :
    - Generation
    - Mutation
    - Saving interesting inputs

- Instrumenting target :
    - Running target functionality, resetting
    - Getting feedback (e.g. Coverage)

- Reporting Crashes

## What a Harness does ?

- Handles feeding the input to the target
    - Calling a specific function in syncbrs.dll that takes input buffer and parses is as a request.

## What is a crash ?

- Till now we finalized our goal is to find crashes, But what is a crash !? 