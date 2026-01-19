# Design Algo Expert
## Question to Think About
### 1. Are we designing the entire AlgoExpert platform or just a specific part of it, like the coding workspace?
- Since we only have about 45 minutes, you should just design the core user flow of the AlgoExpert platform. The core user flow includes users landing on the home page of the website, going to the questions list, marking questions as complete or in progress, and then writing and running code in various languages for each language. Don't worry about payments or authentication; you can just assume that you have these services working already (by the way, we mainly rely on third-party services here, like Stripe, PayPal, and OAuth2).
### 2.  AlgoExpert doesn't seem like a system of utmost criticality (like a hospital system or airplane software); are we okay with 2 to 3 nines of availability for the system?
- Yes, this seems fine--no need to focus too much on making the system highly available.
### 3. How many customers should we be building this for? Is AlgoExpert's audience global or limited to one country?
- AlgoExpert’s website receives hundreds of thousands of users every month, and tens of thousands of users may be on the website at any point in time. We want the website to feel very responsive to people everywhere in the world, and the U.S. and India are the platform's top 2 markets that we especially want to cater to.
### 4. Does AlgoExpert make changes to its content (questions list and question solutions) often?
- Yes--every couple of days on average. And we like to have our changes reflected in production globallywithin the hour.
### 5. This sounds like an internal system. Is there any sense of urgency in deploying this code? Can we afford failures in the deployment process? How fast do we want a single deployment to take?
- This is an internal system, but we'll want to have decent availability, because many outages are resolved by rolling forward or rolling back buggy code, so this part of the infrastructure may be necessary to avoid certain terrible situations. In terms of failure tolerance, any build should eventually reach a SUCCESS or FAILURE state. Once a binary has been successfully built, it should be shippable to all machines globally within 30 minutes.
### 6. 
## Diagram
![AlgoExpert Diagram](../images/algoexpert-system-diagram.svg)
### Explain of the Diagram
#### 1. What This System Is
- This diagram represents a **globally distributed, multi-region online code-execution platform** (think LeetCode / HackerRank–style system):
    - Users authenticate
    - Browse questions
    - Submit code
    - Code is executed securely

- The design emphasizes:
    - Low latency
    - Regional isolation
    - Scalability
    - Fault tolerance
    - Controlled cross-region replication
#### 2. User Entry & Traffic Routing (Bottom)
- **UI / Static Assets**
    - Delivered to users via CDN PoPs