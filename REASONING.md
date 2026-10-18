# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
The coercion ladder rule runs logical, integer, double and turns the whole vector into double because of atomic vector rule, double is higher in priority than integers, which the other items' data type are. The case initializes three items in the vector, therefore length of 3. No matrix or array structure is present so dim is none. 

## P02
The coercion ladder also decides here that since we have a string "2", all values become character, so TRUE is stored as "TRUE" and 1L becomes "1". Has 3 elements and not a matrix so no dimensions.

## P03
R recycles shorter operands, so 1L and 2L are added repeatedly to all elements, becoming [11,22,31,42]. L suffix turns the type to integer. It has 4 elements and is not a matrix so no dimensions.

## P04
Indexing requests values from the vector in order. It asks for the element in 3 and 1 which are integers because of the L suffix, resulting in [third=9,first=8]. It has 2 elements and is not a matrix so no dimensions.

## P05
Indexing request with - sign asks for the elements in those positions be excluded resulting in [4,9] with integer type because of L suffix. It has 2 elements and is not a matrix so no dimensions.

## P06
Logical operator "|" evaluates is.na(x) or x>10L for all elements starting from the first. NA_integer_ is NA with specified type and 12>10 resulting in [NA,12]. It has 2 elements and is not a matrix so no dimensions.

## P07
factor always stores integer codes. Value comes from following Grader Notation. Has 3 elements and is not a matrix so no dimensions.

## P08
typeof() of a list is list. Value comes from following Grader Notation. Has 2 list elements and is not a matrix so no dimensions.

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
The coercion ladder decides that since we have 3.5, the entire vector becomes double, so the logical TRUE becomes 1. Has 3 elements and not a matrix so no dimensions.
