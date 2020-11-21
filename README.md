# maximl-labs

from collections import defaultdict
def SmallestSub(S):
    count = len(set(list(S)))
    n = len(S)
    d= defaultdict(int)
    start = 0
    min_len = float('inf')
    c = 0 
    for j in range(n):
        d[S[j]] += 1
        if d[S[j]] == 1:
            c += 1
        
        if count == c:
            while d[S[start]] > 1:
                if d[S[start]] > 1:
                    d[S[start]] -= 1
                    start += 1
            
            curr_len = j - start + 1
            min_len = min(min_len, curr_len)
    return min_len
 
 
    
 
S = input()
 
ans = SmallestSub(S)
print (ans)
