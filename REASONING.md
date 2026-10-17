# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
The coercion ladder rule runs logical, integer, double and turns the whole vector into double because of atomic vector rule, double is higher in priority than integers, which the other items' data type are. The case initializes three items in the vector, therefore length of 3. No matrix or array structure is present so dim is none. 

## P02
Similarly to P01, the coercion ladder rule runs integer, character, logical and turns the whole vector into characters because "2" is a character, which is the highest among the other data values. The case initializes three items in the vector, therefore length of 3. No matrix or array structure is present so dim is none. 

## P03
Recycling rule makes it so the shorter vector is scanned left to right, an item being added to the longer vector's item, then its next item gets added to the longer vector's next item, and so on; if the shorter vector reaches the end, it starts from the beginning. In this case, the longer vector has 4 items, so a length of 4. Its values were added from 1 and 2, alternating, and as all concerned items are integers, all of them are integers.  No matrix or array structure is present so dim is none. 

## P04
In Intro to R, 2.7 cites the index vectors, where essentially a postive index k x[k] picks position k, starting from index 1. Here, it calls indices 3 and 1, respectively. We get a vector of [9,8], both being integers from the original vector, with length 2 as there were only 2 called indices, with the names disregarded as I believe them to be labels for easier reading. No matrix or array structure is present so dim is none


## P05
Index vectors also covers negative indices, where it will exclude the item in that position in the final vector. Here, it calls index -2, which means we will return a vector of [4,9] since we remove the item in position 2 from the original vector, so 3 - 1 = length 2 in the new vector, both integers, and no matrix or array structure is present so dim is none.

## P06
The missing values rule from 2.5 means `is.na(x)` checks if this item in the vector is `NA`, and | computes logical OR at every position; combined, they can result either in `TRUE | NA` which results in `TRUE` or `FALSE | NA` which results in `FALSE`, then the logical index rule keeps which items resulted in `TRUE`, so the value is [NA,12]. The type is integer because of atomic vector rule as both items are integers, the length is 2, and no matrix or array structure is present so dim is none.

## P07
Factor rule allows a vector having a group within that are grouped and/or classified together, in this case being levels. The value is written following the notation from the manual, so `factor[low,high,low];levels=[low,high]`, and as all of them are characters, we follow atomic vector rule, total length of the factor is 5 including the initial vector combined with the levels. No matrix or array structure is present so dim is none.

## P08
6.1 cites Lists listing components that can be consisted of different types, so this list contains 2 components consisting of a vector and a character. List is its on type, and dimension is not applicable in lists. The values is written following the manual, with top-level being listed as the main components, with their respective sub-values listed as well.

## P09
A data frame is a list of equal-length columns, as stated in R-intro 6.3, so type is a list even though class would be data.frame. length counts the top-level elements, which are the columns, so the length is 2, and the dimensions are the row and column counts, written 2x2. The value is written in the grader's data frame notation with each column's contents.

## P10
Matrix is defined to have 2 rows, and is similiar to data frame such that it's output is like a table; using recycling rule as a reference, from 1-6 it will alternate between the two rows while iterating until it reaches 6, so it 1 will be in 1st row, 2 will be in 2nd row, 3 will be in 1st row, and so on. Atomic vector makes the whole matrix an integer despite being a matrix as no rule is cites matrix being its own data type, length is 6 as we iterated from 1 to 6, and dimension is 2x3 as there are 2 rows, and had 3 columns to finish iterating.

## P11
Mean being called would normally give the mean of the set given by the vector. However, `NA_real_` is present in the vector, and as per missing value rule, any operation with a missing value results in a missing result, hence `NA`. Its type would be a double as per atomic vector rule, with all items being a double including the `NA_real_`,length 0 as result is a `NA` and dimension is not applicable so it is none.

## P12
Unlike P11, `na.rm` is `TRUE`, so it would remove the missing values so it could calculate the mean. Now the resulting vector has 2 items consisting of [8,10] and getting the mean results in 2. The final result then is a double as both items were a double, length of 1, and dimension none as it is not applicable in this context.

## P13
This vector was initialized as [1,2,3], so it would be an integer vector at first. When we assigned x[2] as 2.5, R widened the whole vector to be a double. Now the final vector is [1,2.5,3] with the final type of be a double, length of 3, and dimension none as it is not applicable in this context.

## P14
9.2.1 points out that this would return a vector of the same length as
the condition; first, we check out what value `is.na(scores)` returns: [`FALSE`, `TRUE`, `FALSE`, `FALSE`]. Using these values, we use 0 if condition is true and item*2 if false: [14,0,24,8], then logical vector selects which item has the logical condition true (which is 24 in adjusted[3]) then changes its value to 15. Thus, we have [14,0,15,8] with type double as per atomic vector rule, and dimension none as it is not applicable in this context.

## P15
This array is an atomic vector with its dim attb defined as a vector (from 5.1), which means here, we will have 2 tables with 2 rows and 2 columns. Hence, iterating from 1 to 8, we will then go first from row, then to column, then to table repeating from row->col; making the final value looking like something, so the value is essentially 1-8 divided into 2 tables with 2 rows and 2 columns. All concerned items are integers, so type is integer as per atomic vector rule, length of 8 as defined and dim of 2x2x2 as defined.

## P16
From the zero-index rule, it will return an empty vector as the index selects nothing and will return a zero-length result with the type following the atomic type of the initial vector, which is integer. Due to this, dim is none.