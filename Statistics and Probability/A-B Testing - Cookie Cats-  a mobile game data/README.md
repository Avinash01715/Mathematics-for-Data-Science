## A/B Test Defense — Cookie Cats Dataset

I ran a real A/B test on the Cookie Cats mobile 
game dataset, then had a set of challenge questions 
generated (via Claude) to simulate a skeptical 
stakeholder pushing back on my conclusions.

The questions test statistical judgment, not just 
code execution. My answers below are my own reasoning.

---

### The 7 challenge questions and my answers:

**1. Day-1 isn't significant but Day-7 is. Which do you trust?**  
Day-7. Day-1 could be a fluke of a first session — someone opens the app once out of curiosity regardless of the gate. Day-7 reflects whether someone actually built a habit, which is what a business cares about.

**2. You ran two tests on the same data — doesn't that inflate false-positive risk?**  
Yes, slightly. Running 2 tests raises the chance one shows "significant" purely by chance. With only 2 tests this risk is small, but if I'd run 10 different metrics.

**3. Check sum_gamerounds for outliers — could one player skew this?**  
- **99th percentile:** 493.0  
- **Max:** 49854

**4. Does your confidence interval cross zero?**  
No — for Day-7, the interval is [0.31%, 1.33%]. Since it never touches zero, I'm confident the real effect exists, even though it's small.

**5. Would you actually move the gate back to 30?**  
Based on this data, yes — lean toward gate 30. But retention alone isn't the whole business picture.

**6. Is 0.82 percentage points a big deal or noise?**  
Statistically it's real (CI doesn't cross zero), but practically it's small. For a game with millions of players, even 0.8% retention difference means thousands of extra returning players — so it can matter more than the small number suggests.

**7. Does a t-test really fit binary 0/1 retention data?**  
Not perfectly — a proportions z-test is more textbook-correct for binary outcomes. I used a t-test anyway because with sample sizes this large (44,700 and 45,489), the t-test approximates well. I'm aware of the mismatch rather than ignoring it.