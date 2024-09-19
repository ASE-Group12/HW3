# Easier  AI (just the important bits)


&copy; 2024 Tim Menzies, timm@ieee.org     
BSD-2 license. Share and enjoy.  

----------------------------------

# Claims

- **JJR1**: Nothing works better than 50 random guesses for low-dimensional problems (less than 6 attributes).
- **JJR2**: But such random guessing is rubbish for higher-dimensional data. Let us test that.

## Outputs when we run `rq.sh` for high and low-dimensional data using our `extend.py` file:

![More than 6 dimension](output\image\high_output.png)

![Less than 6 dimension](output\image\low_output.png)

---

## Summary of results:


1. **Ranks**:
    - In both high and low-dimensional data, `exploit/b=True` and `explore/b=True` dominate, outperforming `rrp` and `asIs`. 
    - However, in low dimensions, `rrp` performs better, especially in ranks 0 and 1.

2. **Evals**:
    - For high dimensions, `exploit/b=True` shows the highest evaluations across ranks.
    - In low dimensions, `rrp` has more evaluations, supporting the idea that random guessing works better in simpler cases.

3. **Deltas**:
    - `Exploit/b=True` and `explore/b=True` show significant improvements over the baseline in high dimensions, while improvements are less in low dimensions.
    - `Rrp` shows some improvement in ranks 0 and 1 in low dimensions.

---

## Conclusion:

We confirm **JJR1** (random guessing works in low dimensions) and **JJR2** (random guessing fails in high dimensions). 
- `Exploit/b=True` consistently outperforms random guessing, especially in high dimensions, confirming **JJR2**.
- No hypothesis refinement is needed.