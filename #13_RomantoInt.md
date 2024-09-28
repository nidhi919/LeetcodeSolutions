Leetcode #13: Roman Numeral to Int

class Solution(object):
    def romanToInt(self, s): 

        romanmap = {'I':1, 'V':5, 'X':10, 'L':50, 'C':100, 'D':500, 'M':1000}  //dictionary to map roman numerals to integer values

        a = len(s)    //length of input
        sum = romanmap[s[a-1]]   //result

        for i in range(a-2, -1, -1):  
            if romanmap[s[i]] >= romanmap[s[i+1]]:    
                sum+= romanmap[s[i]]
            else:
                sum-=romanmap[s[i]]
        
        return sum
