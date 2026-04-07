# Thundering Herd Challenge

When cache fails, everything breaks.

This repository serves as a **long-term reference** for understanding and dealing with one of the most common problems in backend systems:

> **The Thundering Herd Problem (Cache Stampede)**

For participation details, timeline, and reward information, see the [official blog post](https://holydev.uk/concurrency/challenge-thundering-herd-cache-stampede/).

---

## What is this challenge about?

Imagine you are building an API: `GET /api/product/{id}`

Your system:
- Reads data from a database (~100ms latency)
- Uses cache (in-memory, Redis, or similar)

---

## The Problem

At some point, the cache expires (or misses).

Suddenly:

- Hundreds or thousands of requests hit the same key simultaneously
- All of them go directly to the database
- Database gets overwhelmed
- Latency spikes
- The system may collapse

This is known as:

> **The Thundering Herd Problem (a.k.a Cache Stampede)**

---

## Your Goal

This is **not just a coding challenge**.

The goal is to:

- Understand the problem deeply
- Reproduce it in a test system
- Explain it clearly in your own words
- Propose a solution with reasoning

👉 Your **thought process matters more than the code itself**.

---

## What you need to do

### 1. Reproduce the problem

Build a system where:

- A cache miss causes multiple concurrent requests
- All requests hit the database for the same key

You can simulate load using tools like:

- JMeter  
- k6  
- Custom scripts

Show that:

- The same data is fetched multiple times  
- The system degrades under load  

---

### 2. Explain the problem

In your README, answer:

- What is the Thundering Herd problem?  
- Why does it happen?  
- When does it become dangerous?  
- What factors make it worse?  

👉 Explain in your own words, clearly and concisely.

---

### 3. Implement ONE solution

Choose at least one approach to mitigate the problem. Examples (optional):

- Mutex / per-key locking  
- Request coalescing  
- SingleFlight (or equivalent)  
- Cache strategies (TTL, soft TTL, etc.)  

👉 The solution doesn’t have to be perfect, but it must be **well understood**.

---

### 4. Explain your solution

Describe:

- Why your solution works  
- What trade-offs it introduces  
- When it might fail  

---

### 5. Record a video (required)

Show:

- What you understood  
- What you built  
- Why you made your decisions  

👉 No need for fancy editing. Clarity matters.

---

## 🔓 Freedom

- Any programming language  
- Any tools or libraries  
- No “correct” answer  

This is an **open challenge** and an **open-source learning resource**.

---

## Hint

If your solution feels too simple, increase the load or concurrency.

---

## Bonus ideas (optional)

- Compare before vs after metrics  
- Try multiple solutions  
- Simulate multi-instance systems  
- Explore distributed locking (e.g., Redis)  
- Consider hot keys  

---

## Final Note

This README is meant as a **long-term reference** for anyone learning about the Thundering Herd problem.

The challenge is not just about code:

- Show how you think  
- How you analyze systems  
- How you explain trade-offs  

Every clear, insightful explanation has value. Future readers can learn from your approach, understand the reasoning, and see different ways to solve the same problem.

Good luck. 🚀
