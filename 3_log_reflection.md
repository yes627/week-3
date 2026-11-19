# Auditing an AI interpretation of a price table

## 1. Draft AI interpretation 

1. Sweetener D has the highest average price (576.81).
2. Oil B and Pulse C have means almost equal to their medians.
3. Because of that, Oil B and Pulse C prices are stable.
4. Staple A's mean is well above its median, so a few high prices pull it up.
5. Sweetener D's mean is more than three times its median, so it has outliers.
6. Staple A is the cheapest item on both measures.
7. The items rank the same way by mean and by median.
8. Sweetener D rose the most (19.41%), probably because of supply shortages.
9. Pulse C is the most stable item because it rose only 2.43%.
10. Sweetener D's typical price is its median, 167.75, not its mean.
11. Inflation drove the increases across all four items.

Key: GREEN = recomputable from the table. AMBER = an explanation (plausible, not shown by the data). RED = causal claim, or refers to data not shown.

## 2. Audit table


| # | Claim | Colour | How I checked | Verdict |
|---|---|---|---|---|
| 1 | D has the highest mean | Green | 576.81 > 324.83 > 205.91 > 158.71 | Accepted |
| 2 | Oil B and Pulse C: mean ≈ median | Green | Oil B: 324.83 − 324.00 = 0.83 (0.26% of the median). Pulse C: 205.91 − 206.00 = −0.09 (0.04%) | Accepted |
| 3 | …so those prices are "stable" | Amber | Mean ≈ median says the distribution is roughly symmetric. It says nothing about how much prices move over time | Rejected |
| 4a | Staple A mean is well above its median | Green | 158.71 − 112.50 = 46.21; 158.71 / 112.50 = 1.411, so 41% above | Accepted |
| 4b | …because a few high prices pull it up | Amber | Consistent with right skew, but a cluster of moderately high prices would do the same | Accepted with hedge ("consistent with") |
| 5a | D's mean is over 3× its median | Green | 576.81 / 167.75 = 3.44 | Accepted |
| 5b | …so D has outliers | Amber | Could be a few extreme values or a second, much pricier group (for example a premium variant). Cannot tell from two numbers | Rejected as stated |
| 6 | A is cheapest on both measures | Green | Lowest mean (158.71) and lowest median (112.50) | Accepted |
| 7 | Same ranking by mean and median | Green | By mean: D > B > C > A. By median: B > C > D > A. D drops from 1st to 3rd | **Rejected** (false) |
| 8a | D rose the most | Green | 19.41 > 15.28 > 12.98 > 2.43 (ranking only; the 19.41 itself is taken as given) | Accepted |
| 8b | …because of supply shortages | Red | No supply, demand or date data was shown | Rejected |
| 9 | Pulse C is "most stable" | Amber | First-to-last uses two data points. A series can swing wildly and end near where it began | Rejected |
| 10 | D's typical price is the median 167.75 | Amber | Far better than the mean here, but "typical" depends on the shape. If prices cluster in two groups, no single number is typical | Accepted with hedge |
| 11 | Inflation drove all increases | Red | No inflation data, no comparison group | Rejected |

Tally: 14 claims checked; 8 accepted outright or with a hedge, 6 rejected. The planted error is claim 7.

## 3. Explaining to the classmate ("the mean is always the typical price")

**Excerpt (saved):**

**Classmate:** The mean is the average. Average means typical. Why would the table even show a median?

**Me:** Take five prices: 100, 100, 110, 120, 1000. The mean is 286. The median is 110. How many of those five prices are anywhere near 286?

**Classmate:** None. But why is it 286 then?

**Me:** Because the mean adds up the *size* of every number. That one 1000 contributes 1000 to the total, so it drags the mean up. Think of a seesaw: the mean is where it balances, and one heavy weight far out moves the balance point a long way.

**Classmate:** But why does it count the size? That seems unfair to the normal prices.

**Me:** It isn't unfair, it's answering a different question. The mean answers: "if every item cost the same and the total bill stayed the same, what would that price be?" Check it: 5 × 286 = 1430, which is exactly the real total. So the mean is the right number when you care about the *total*, such as a budget for buying all five.

**Classmate:** And the median?

**Me:** The median only uses order. Sort the prices and take the middle one. It ignores how big the biggest one is, so one extreme price can't move it. It answers: "what does the middle item cost?"

**Classmate:** But why would "the middle" be typical?

**Me:** Half the items cost less and half cost more, so you are never far off the crowd. "Typical" here means "the one you most likely meet". When prices are roughly symmetric, mean and median agree, which is why Oil B shows 324.83 against 324.00 and it doesn't matter. When they disagree, the data is lopsided. Look at Sweetener D: mean 576.81 against median 167.75. The mean is 3.44 times the median. If you quote 576.81 as "the price", you describe almost no actual item.

**Classmate:** So the mean is wrong?

**Me:** No. It is right for totals and misleading for typical. The question to ask is always: *what am I going to do with this number?* Budget for all of them: mean. Guess what one item costs: median. And when the two disagree a lot, report both and say why.

**Check question for you:** Staple A has mean 158.71 and median 112.50. A shopper buys one item at random. Which number would you quote them, and why?

*(The questions stopped repeating once the confusion was named: "typical" and "balances the total" were being treated as the same thing.)*

## 4. Reflection: where did my first draft say more than the data allowed?

- **Causes (8b, 11):** I explained *why* prices moved with no data on causes. A table of means, medians and two-point changes cannot support any cause.
- **"Stable" and "most stable" (3, 9):** I turned a symmetry fact (mean ≈ median) and an endpoint change into a claim about volatility. Neither measures volatility.
- **"Outliers" (5b):** Mean much greater than median shows skew. Naming the reason (outliers) needed the raw values.
- **"Typical" (10):** I treated the median as the answer. It is only a better summary for this shape, and I never saw the shape.
- **Ranking (7):** The opposite error: I assumed the two statistics would agree, and the table contradicts that. Checking against the numbers caught it.
- **Pattern:** Every overreach was a jump from a *summary number* to a statement about *individual observations or the world*. The audit rule that worked: for each sentence, ask "which cell of the table is this?" If no cell, it is amber or red.