# SOB21_Challenge
My solution for the Summer of Bitcoin Challenge 2021!


1st Approach - Brute force using iteration see [Here](https://github.com/Uttam-Singhh/SOB21_Challenge/blob/main/sob_bruteforce.ipynb)


2nd Approach - Optimized using greedy Method see [Here](https://github.com/Uttam-Singhh/SOB21_Challenge/blob/main/soc_optmized.ipynb)


3rd Approach - Using Dynamic Programming! (0 1 Knapsack Problem - Max weight and Max Profit)


SUDO CODE for 0 1 knapsack Problem- 3rd Approach(Was not able to implement due to lack of time)
```
def knapsack(v, w, W):
 
    # `T[i][j]` stores the maximum value of knapsack having weight less
    # than equal to `j` with only first `i` items considered.
    T = [[0 for x in range(W + 1)] for y in range(len(v) + 1)]
 
    # do for i'th item
    for i in range(1, len(v) + 1):
 
        # consider all weights from 0 to maximum capacity `W`
        for j in range(W + 1):
 
            # don't include the i'th element if `j-w[i-1]` is negative
            if w[i - 1] > j:
                T[i][j] = T[i - 1][j]
            else:
                # find the maximum value we get by excluding or including the i'th item
                T[i][j] = max(T[i - 1][j], T[i - 1][j - w[i - 1]] + v[i - 1])
 
    # return maximum value
    return T[len(v)][W]                                                                                                  Source - Techie Delight
    
    ```
