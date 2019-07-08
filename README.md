# Python-length-program

#python 3.5.2
no = 256
def max_distinct_char(str, n): 
    count = [0] * no
    for i in range(n):
        count[ord(str[i])] += 1
    max1 = 0
    for i in range(no): 
        if (count[i] != 0): 
            max1 += 1
    return max1
def smallesteSubstr_maxDistictChar(str): 
    n = len(str) 
    max1 = max_distinct_char(str, n) 
    minl = n     
    for i in range(n): 
        for j in range(n): 
            subs = str[i:j] 
            subs_lenght = len(subs) 
            sub_distinct_char = max_distinct_char(subs,subs_lenght) 
            if (subs_lenght < minl and max1 == sub_distinct_char): 
                minl = subs_lenght 
    return minl
if __name__ == "__main__":
  str = input().lower()
  l = smallesteSubstr_maxDistictChar(str); 
  print( l) 
 

