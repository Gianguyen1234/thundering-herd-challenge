# Thundering Herd Challenge

When cache fails, everything breaks.

This challenge is about understanding and dealing with one of the most common problems in backend systems:

> **The Thundering Herd Problem**

---

## What is this challenge about?

Imagine you are building an API: GET /api/product/{id}


Your system:
- Reads data from a database (~100ms latency)
- Uses cache (in-memory or Redis)

---

## The Problem

At some point, the cache expires (or misses).

Now suddenly:

- Hundreds or thousands of requests hit the same key
- All of them go directly to the database
- The database gets overwhelmed
- Latency spikes
- The system may collapse

This is known as:

>  **Thundering Herd Problem (a.k.a Cache Stampede)**

---

## Your Goal

This is **not a coding challenge only**.

The goal is to:

- Understand the problem deeply
- Reproduce it
- Explain it clearly
- Propose a solution

👉 Your thinking matters more than your code.

---

## What you need to do

### 1. Reproduce the problem

Build a simple system where:

- Cache miss causes multiple concurrent requests
- All requests hit the database for the same key

You can simulate load using:
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

👉 Explain it in your own words.

---

### 3. Implement ONE solution

Choose at least one approach to mitigate the problem.

Examples (not required):
- Mutex / per-key locking
- Request coalescing
- SingleFlight
- Cache strategies (TTL, soft TTL, etc.)

👉 It doesn’t have to be perfect.  
👉 It must be **well understood**.

---

### 4. Explain your solution

Describe:

- Why your solution works
- What trade-offs it introduces
- When it might fail

---

### 5. Record a video (required)

Explain your solution in a short video:

- What you understood
- What you built
- Why you made your decisions

👉 No need for editing. Just be clear.

---

## 🔓 Freedom

- No restriction on programming language
- No restriction on tools
- No “correct” answer

This is an **open challenge**.

---

##  Hint

If your solution feels too simple…

Try increasing the load.

---

##  Bonus ideas (optional)

- Compare before vs after
- Try multiple solutions
- Simulate multi-instance systems
- Explore distributed locking (e.g., Redis)
- Think about hot keys

---

## Final Note

This is not about submitting something “that works”.

It’s about showing:
- How you think
- How you analyze systems
- How you explain trade-offs

---

Good luck. 🚀
