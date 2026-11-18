## 1. The numbers
| Item | Mean | Median | Percentage Change  first to last week |
| Oil B | 324.83 | 324.0 | about +15% |
| Pulse C | 205.91 | 206.0 | about +2.5% |
| Staple A | 158.71 | 112.5 | about +13% |
| Sweetener D | 576.81 | 167.75 | about +19% |

Pulse C is missing one price (City 2, 1 Jan), so its change is measured from 8 Jan instead.

## 2. What I'd report for each item

- Oil B: the % change. Prices climb steadily, so an average just tells you the middle of the window, and the mean and median are almost the same anyway.
- Pulse C: the median (206). Prices barely move, so it's a fair picture of the typical price.
- Staple A: the median (112.5). One flagged price of 1,250 pushes the mean up to 158.71, but the median doesn't budge.
- Sweetener D: the median (about 167.5). One flagged price of 9,999 makes the mean look like prices are over 570 when they're really around 167.

## 3. With and without a flagged value (Sweetener D)

| | Mean | Median |
| With the 9,999 | 576.81 | 167.75 |
| Without it | 167.15 | 167.50 |

A single odd entry shifts the mean by about 410 but the median by only 0.25. The mean counts how big every number is, so one huge one drags it. The median only cares about the order, so the huge one is just "the biggest". The flagged values are probably typing errors, but the file doesn't say, so I'd exclude them and mention it rather than quietly delete them.

## 4. Referee's note

**O** = observation, **E** = possible explanation, **C** = causal claim

1. **O:** The data has 96 rows, and every one is labelled as illustrative teaching data.
2. **O:** Four rows are flagged: one missing price, two extreme values (1,250 and 9,999) and one row relabelled from Oil B to Staple A.
3. **O:** Dropping the 9,999 changes the Sweetener D mean from 576.81 to 167.15 but the median by only 0.25.
4. **O:** Oil B rose about 15% and Sweetener D about 19%, while Pulse C stayed nearly flat.
5. **E:** The two extreme values may be typing errors, like an extra digit or a placeholder, but the file doesn't confirm that.
6. **E:** The relabelled row may have been entered under the wrong item, though its price fits Staple A, which doesn't prove it.
7. **E:** The missing Pulse C price may simply mean it wasn't collected that week.
8. **C (not supported):** Saying "Oil B went up because of a supply shock" isn't possible from this file.
9. **O:** The file only has prices, with nothing on supply, costs or demand, so it can't show why any price moved.
10. **O:** I'd suggest the author note how each flag was handled and whether the relabelled row was checked against the source.