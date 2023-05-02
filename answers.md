# CMPS 2200 Assignment 5
## Answers

**Name:** Tyler Simms


Place all written answers from `assignment-05.md` here for easier grading.





- **1a.**

A greedy algorithm for producing as few coins as possible that sum to N is to start at the highest possible denomination, 2^k, that is less than N, choose one of those coins, subtract 2^k from N, and then repeat the process for each descending denomination until the coins sum to N. This algorithm will always work because the coins are in denominations that are consistently powers of 2, so any difference between the accumulated sum and N can be eliminated. This algorithim is optimal and will always produce the fewest possible coins assuming that value of k can go as high as necessary, meaning that there is always a greater denomination that is a power of 2. This algorithm satisfies both the greedy choice property and the optimal substructure property.

Where v is the value of the highest coint denomination that is below N: v(OPT([2^k],N)) = max{v(2^k) + v(OPT([2^k-1], N-2^k)), v(OPT([2^k−1],N))}


- **1b.**

The work and span of this algorithm are both O(logn). The span is the same because this algorithm cannot be parallelized.


- **2a.**

If N is 15 and the denominations are 1, 6, 9, and 12, the greedy algorithm will decide to take one 12 and three 1s. This amount is four coins in total. However, this solution is not optimal because the optimal solution only requires two coins, one 6 and one 9. The greedy algorithm does not work because there is no distinct pattern between the denomination amounts. We cannot assume that the greedy choice property and optimal substructure property apply in this situation.

- **2b.**

Bottom-up memoization using a table of smaller subproblems would work best for a dynamic programming algorithm in this situation. The base case would be a sum in dollars equal to 1. Each subproblem would involve a value from 1 through N, incrementing by one each subproblem. In each subproblem, the value in the table would be the smallest possible amount of coins to reach the given dollar value. As a result, each subsequent subproblem only requires finding the smallest amount of coins that account for the difference between the current dollar value and the previous dollar value. When finding the overall optimal solution, the solutions to the subproblems can easily be combined without having to recalculate anything. The work and span of this algorithm are both O(n). The span is the same because this algorithm cannot be parallelized.


- **3a.**

Done in main.py.




- **3b.**

Done in main.py.




- **3c.**

Done in main.py.

