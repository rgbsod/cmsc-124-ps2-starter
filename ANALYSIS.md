# Vector and Scalar Evaluation
### Trace Vector Eval
Lets take input c(Ada=8,Grace=NA_real_,Linus=12,Barbara=4)

When we run this input through `clean_scores_vector()`, the function's operations look at and act on all the elements at once. First it looks at all the elements and turns all NA values it finds into 0. Then it multiplies the entire vector by 2. Then it looks at all elements for values over 20 and turns them into 20 for the cap. Finally c(Ada=16,Grace=0,Linus=20,Barbara=8) is returned.


### Trace Scalar Eval
Unlike vector, `clean_scores_scalar()` will reach Grace on pass 2.

Before the loop, `out <- setNames(as.double(scores), names(scores))` copies the scores into a double vector and keeps the names. 

At i = 1, `is.na` check is FALSE for Ada's 8, so the else branch runs `min(2 * v, 20)`. Doubling gives 16, which is under 20, it is returned as is, and `out[[i]] <- ...` stores it at position 1 with the name Ada attached.

At i = 2, v is Grace's NA, so `is.na(v)` is TRUE and the if branch returns 0 directly. The doubling and the min are never evaluated for this position, and is stored in position 2 with the name Grace attached.

At i = 3 and i = 4, `is.na(v)` is FALSE, so min(2 * v, 20) runs: Linus's 24 exceeds the cap, so min returns 20, and Barbara's 8 stays 8. Each result is stored at its own position, so the names stay attached.

### Questions
1. Everything that happens in `clean_scores_vector()` acts on all elements at once.
   
2. The loop makes evaluation order visible at pass 2. Only position 1 of `out` has been cleaned, while positions 2-4 still hold the raw scores, including Grace's NA. A debugger that stopped there would show the vector half-cleaned.

3. Suppose we meant to add c(5,10,15,25) to c(10,20,30,40), but accidentally wrote only c(5,10) for the first vector. The result would be c(15,30,35,50) instead of c(15, 30, 45, 65), with the third and fourth item being different from the intended answer due to R recycling the first vector as (5,10,5,10).

4. In a real R program, we would keep the vector version. R is an interpreted language and loops become inefficient when it has to run each interation manually over and over. While loops are indeed present in R since it is also a functional programming language, vector operations for columns of data are usually the go-to for R. The tradeoff is that while it is easier to read and overall faster, giving up loops also means giving up tasks that are done sequentially through data. 

