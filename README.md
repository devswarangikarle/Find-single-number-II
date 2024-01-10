# Find-single-number-II
You're given an integer array, in which each element is present thrice except for one.  Find the number that is present only once.

def find_single_number(arr):
    result = 0
    
    
    for i in range(32):
        count = 0
        for num in arr:
            count += (num >> i) & 1
        
       
        if count % 3 != 0:
            result |= (1 << i)
    
    return result

try:
 
    n = int(input())
    arr = list(map(int, input().split()))

   
    result = find_single_number(arr)
    print(result)

except EOFError:
    print("Error: EOF when reading a line. Make sure to provide valid input.")
