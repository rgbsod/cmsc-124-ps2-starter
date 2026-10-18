# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
The coercion ladder decides that since we have 3.5, the entire vector becomes double, so the logical TRUE becomes 1. Has 3 elements and not a matrix so no dimensions.

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
typeof() of a data.frame is also list. Value comes from following Grader Notation.Has 2 list elements and since data.frame acts like a table that is a list of columns, it becomes a matrix with dimensions 2x2

## P10
matrix here as puts integers 1 to 6 in 2 rows which are then added to by recycled values of 10 and 20 resulting in matrix(2x2)[11,22,13,24,15,26] which also comes from Grader Notation. It has 6 elements in total and is a matrix with 2x3 dimensions.

## P11
mean() returns missing if any of the elements are missing. Type becomes double since NA is specified as real and 8 and 10 have no L suffix so they are double by default. It is not a matrix so it has no dimensions.

## P12
na.rm = TRUE removes all missing values, mean returns 9 with type double as default. It is not a matrix so it has no dimensions

## P13
Subassignment of 2.5 to an integer type vector makes the whole vector type double. Has 3 elements and is not a matrix so it has no dimensions.

## P14
ifelse() function evaluates each element in scores to turn into 0 when NA and multiply by 2 for any other case. The following line turns all elements greater than 15 into 15 resulting in [14,0,15,8] with type double as default. It has 4 elements and is not a matrix so it has no dimensions.

## P15
array() here is assigned with integer values from 1 to 8 with set dimensions 2x2x2. It has 8 elements and has dimensions 2x2x2.

## P16
Indexing in R starts from 1, so asking for the 0 index of a vector returns an empty vector with the same type and length 0.
