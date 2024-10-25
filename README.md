# Ravi-s-Quest-for-Perfect-Squares

In a distant kingdom, a wise mathematician named Ravi has been given a challenging task by the king. The king provides Ravi with an integer n and asks him to figure out the least number of magical stones, called "perfect squares," that can be combined to sum exactly to n.
A perfect square is a stone that is formed by multiplying a number by itself. For example, stones with values like 1, 4, 9, and 16 are perfect squares, while 3 and 11 are not.
Ravi must determine the smallest number of perfect square stones that, when added together, will give the king's number n. Can you help Ravi solve this puzzle and impress the king?

import math

def min_squares(n):

    dp = [float('inf')] * (n + 1)
    dp[0] = 0  
    
    for i in range(1, n + 1):
        j = 1
        while j * j <= i:
            dp[i] = min(dp[i], dp[i - j * j] + 1)
            j += 1
    
    return dp[n]
n = int(input().strip())
print(min_squares(n))
