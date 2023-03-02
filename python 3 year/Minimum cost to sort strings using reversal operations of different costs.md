# GFG

## Minimum cost to sort strings using reversal operations of different costs

*Given an array of strings and costs of reversing all strings, we need to sort the array. We cannot move strings in array, only string reversal is allowed. We need to reverse some of the strings in such a way that all strings make a lexicographic order and cost is also minimized. If it is not possible to sort strings in any way, output not possible*

    Input  : arr[] = {“aa”, “ba”, “ac”}, 
          reverseCost[] = {1, 3, 1}

    Output : Minimum cost of sorting = 1
    Explanation : We can make above string array sorted 
    by reversing one of 2nd or 3rd string, but reversing
    2nd string cost 3, so we will reverse 3rd string to 
    make string array sorted with a cost 1 which is 
    minimum.
