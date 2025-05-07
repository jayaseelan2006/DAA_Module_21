# EX 3B Hamiltonian Circuit Problem
## DATE:
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1.Start from each vertex and initialize the path list.
2.Use isSafe() to check if the next vertex is adjacent and not already visited.
3.Recursively build the path by trying all vertices one by one.
4.If the path includes all vertices, a Hamiltonian path exists.
5.If found, print "YES"; otherwise, print "NO" after checking all starting points.



/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: jayaseelan U
Register Number:  212223220039
*/

## Program:
```
def isSafe(adj,p,v,pos):
    if pos>0 and adj[p[pos-1]][v]==0:
        return False
    if v in p:
        return False
    return True
def HMU(adj,N,p,pos):
    if pos==N:
        return True
    for v in range(N):
        if isSafe(adj,p,v,pos):
            p.append(v)
            if HMU(adj,N,p,pos+1):
                return True
            p.pop()
    return False
def Hamiltonian_path(adj, N):
    for s in range(N):
        p=[s]
        if HMU(adj,N,p,1):
            return True
    return False
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:
![437673623-e426b254-a17d-4f25-aa48-1b84a6c22fa0](https://github.com/user-attachments/assets/e0f9a343-c668-4bc8-98b2-a149f8b64357)

## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
