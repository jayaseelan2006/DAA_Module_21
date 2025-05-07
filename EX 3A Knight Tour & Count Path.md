# EX 3A Knight Tour & Count Path
## DATE:
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
```
1.Initialize movement directions for the knight (dx and dy).
2.Use BFS starting from the knight's position and mark it as visited.
3.Dequeue the current position and check if it's the target position.
4.For each valid move, check if the cell is within bounds and unvisited, then enqueue it with an 
  incremented distance.
5.If the target is reached, return the distance; otherwise, return -1 if no path exists.
```

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: Jayaseelan U
Register Number:  212223220039
*/
```
## Program:
```
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,targetpos, N):
    dx = [2, 2, -2, -2, 1, 1, -1, -1]
    dy = [1, -1, 1, -1, 2, -2, 2, -2]
    queue = []
    
    queue.append(cell(knightpos[0], knightpos[1], 0))
    
    visited = [[False for i in range(N + 1)] 
                      for j in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True
    while queue:
        current = queue.pop(0)
        
        if (current.x == targetpos[0] and 
            current.y == targetpos[1]):
            return current.dist
        
        for i in range(8):
            x = current.x + dx[i]
            y = current.y + dy[i]
            
            if (isInside(x, y, N) and not visited[x][y]):
                visited[x][y] = True
                queue.append(cell(x, y, current.dist + 1))
    
    return -1
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,targetpos, N))

```

## Output:
![437673285-91cd0ff2-7c69-4b16-b151-e7fe6e26cf11](https://github.com/user-attachments/assets/122a45c3-5343-44e1-a45d-dd97c55f5021)




## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
