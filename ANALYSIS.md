# Vector and Scalar Evaluation
### Trace Vector Eval
TODO

### Trace Scalar Eval
Unlike vector, `clean_scores_scalar()` will reach Grace on pass 2.

Before the loop, `out <- setNames(as.double(scores), names(scores))` copies the scores into a double vector and keeps the names. 

At i = 1, `is.na` check is FALSE for Ada's 8, so the else branch runs `min(2 * v, 20)`. Doubling gives 16, which is under 20, it is returned as is, and `out[[i]] <- ...` stores it at position 1 with the name Ada attached.

At i = 2, v is Grace's NA, so `is.na(v)` is TRUE and the if branch returns 0 directly. The doubling and the min are never evaluated for this position, and is stored in position 2 with the name Grace attached.

At i = 3 and i = 4, `is.na(v)` is FALSE, so min(2 * v, 20) runs: Linus's 24 exceeds the cap, so min returns 20, and Barbara's 8 stays 8. Each result is stored at its own position, so the names stay attached.

### Questions
1. TODO
   
2. The loop makes evaluation order visible at pass 2. Only position 1 of `out` has been cleaned, while positions 2-4 still hold the raw scores, including Grace's NA. A debugger that stopped there would show the vector half-cleaned.

3. Suppose we meant to add c(5,10,15,25) to c(10,20,30,40), but accidentally wrote only c(5,10) for the first vector. The result would be c(15,30,35,50) instead of c(15, 30, 45, 65), with the third and fourth item being different from the intended answer due to R recycling the first vector as (5,10,5,10).

4. TODO

