Decomposition Problem using DFS/BFS
===

Some problem asks for an optimal way to decomposite the input as a "sum" of many terms

LC279. Perfect Squares
---
Given a positive integer n, find the least number of perfect square numbers (for example, 1, 4, 9, 16, ...) which sum to n.

BFS solution
```
    def numSquares(self, n):
        i, f = 1, []
        while i * i <= n:
            f.append(i * i)
            i += 1
        
        bfs = [(0, n)]
        vis = set([n])
        for step, num in bfs:
            if num == 0: return step
            for sqr in f:
                if num - sqr >= 0 and num - sqr not in vis:
                    vis.add(num - sqr)
                    bfs.append((step + 1, num - sqr))
        return -1
```

DFS solution
```

```

LC964. Least Operators to Express Number
---
