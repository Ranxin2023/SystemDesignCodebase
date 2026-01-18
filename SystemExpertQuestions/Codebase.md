# Design A Code-Deployment System
## Question to Think About
### 1. What exactly do we mean by a code-deployment system? Are we talking about building, testing, and shipping code?
### 2. What part of the software-development lifecycle, so to speak, are we designing this for? Is this process of building and deploying code happening when code is being submitted for code review, when code is being merged into a codebase, or when code is being shipped?
### 3. Are we essentially trying to ship code to production by sending it to, presumably, all of our application servers around the world?
### 4. How many machines are we deploying to? Are they located all over the world?
### 5. This sounds like an internal system. Is there any sense of urgency in deploying this code? Can we afford failures in the deployment process? How fast do we want a single deployment to take?
### 6. So it sounds like we want our system to be available, but not necessarily highly available, we want a clear end-state for builds, and we want the entire process of building and deploying code to take roughly 30 minutes. Is that correct?
### 7. How often will we be building and deploying code, how long does it take to build code, and how big can the binaries that we'll be deploying get?
### 8. When building code, how do we have access to the actual code? Is there some sort of reference that we can use to grab code to build?

## Answer
### 1. Gathering System Requirements
- As with any systems design interview question, the first thing that we want to do is to gather system requirements; we need to figure out what system we're building exactly.
- From the answers we were given to our clarifying questions (see Prompt Box), we're building a system that involves repeatedly (in the order of thousands of times per day) building and deploying code to **hundreds of thousands of** machines spread out across 5-10 regions around the world.
- Building code will involve grabbing snapshots of source code using commit SHA identifiers; beyond that, we can assume that the actual implementation details of the building action are taken care of. In other words, we don't need to worry about how we would build JavaScript code or C++ code; we just need to design the system that enables the repeated building of code.
### 2. Coming Up With A Plan
- It's important to organize ourselves and to lay out a clear plan regarding how we're going to tackle our design. What are the major, distinguishable components of our how system?
- It seems like this system can actually very simply be divided into two clear subsystems:
    - the Build System that builds code into binaries
    - the Deployment System that deploys binaries to our machines across the world

### System Diagram
![Code Deployment Diagram](images/code-deployment.md) 