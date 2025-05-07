# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
```
1.Input two strings: the main string s1 and the pattern s2.
2.Loop through s1 from index 0 to len(s1) - len(s2) to check every possible starting position.
3.At each index, extract a substring of length len(s2) from s1.
4.Compare the substring with s2.
5.If a match is found, return the starting index; otherwise, the function ends without match (implicitly returns None).
```  





## Developed by: Jayaseelan U
## Register Number:  212223220039

## Program:
```
def BF(s1,s2):
     for i in range(len(s1)-len(s2)+1):
         if s1[i:i+len(s2)]==s2:
             return i

a1=input() 
a2=input() 
b=BF(a1,a2)
print(b)

```

## Output:
![437674006-a0f756ea-1fb5-4eb2-8117-243b42f189cd](https://github.com/user-attachments/assets/52995e83-b31e-4323-bd88-5060c74ece6b)




## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
