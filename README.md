## Q1 — Digit Gatekeeper (`q1.html`)

**Approach:**
Iterate over every integer `x` from `L` to `R`. For each `x`, check three conditions:
1. `x % K === 0` — divisible by K
2. The sum of digits of `x` is a prime number (checked with a helper `isPrime`)
3. `x` contains no digit `0` (checked by reading digits one by one)

Count and display all integers that satisfy all three conditions.

**Time Complexity:** O((R − L + 1) × d) where d = number of digits ≈ O(R × log R)  
**Space Complexity:** O(1)

---

## Q2 — Roll-Seed Lock (`q2.html`)

**Approach:**
Start with `current = N`. Repeat exactly 3 times:
- If `current` is even → `current = floor(current / 2) + seed`
- If `current` is odd  → `current = current * 3 − seed`

After 3 steps, check:
- `100 ≤ current ≤ 999` (it is a 3-digit number)
- The middle digit (tens place) equals `seed`

Print `YES, <number>` or `NO, <number>` accordingly.

**Time Complexity:** O(1) — exactly 3 fixed iterations  
**Space Complexity:** O(1)

---

## Q3 — Mirror Corridor (`q3.html`)

**Approach:**
Iterate `X` from `0` to `100000`. For each `X`, compute `val = N + X` and check:
1. `val` is a palindrome — convert to string, compare with its reverse
2. `val % K === 0`

Return the first `X` that satisfies both, or `-1` if none found.

**Time Complexity:** O(100000 × log(N + 100000)) ≈ O(1) bounded search  
**Space Complexity:** O(log N) for the string representation

---

## Q4 — Fare Calculator (`q4.html`)

**Approach:**
Apply each pricing rule in sequence:
1. `fare = base + 7 × distance`
2. If `minutesLate > 15`, add 20
3. If `distance > 10`, add `floor(10% of fare)`
4. If `seed` is odd, subtract `seed`; otherwise add `seed`
5. Round `fare` up to the nearest multiple of 5: `ceil(fare / 5) * 5`

**Time Complexity:** O(1)  
**Space Complexity:** O(1)

---

## Q5 — Skipping Numbers (`q5.html`)

**Approach:**
Compute `divisor = seed + 2`. Increment `m` from 1 upward, adding `m` to a running `sum` only when `m % divisor !== 0`. Stop as soon as `sum ≥ N`. Output both `m` and `sum`.

**Time Complexity:** O(m) where m is the answer; in the worst case O(N) since skipped terms reduce density  
**Space Complexity:** O(1)

---

## Q6 — Contest Score Judge (`q6.html`)

**Approach:**
1. Compute raw `score = 3a + b − 2c`
2. If `score < 0`, clamp it to `0`
3. If `a + b + c > 50`, subtract `10`
4. If `score ≥ 60` → `PASS`, else → `FAIL`

**Time Complexity:** O(1)  
**Space Complexity:** O(1)

---

## File Structure

```
Assignment 4/
├── q1.html   — Digit Gatekeeper
├── q2.html   — Roll-Seed Lock
├── q3.html   — Mirror Corridor
├── q4.html   — Fare Calculator
├── q5.html   — Skipping Numbers
├── q6.html   — Contest Score Judge
└── README.md — This file
```
