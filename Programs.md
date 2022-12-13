# Given a string, find the length of the longest substring without repeating characters.


        def lengthOfLongestSubstring(s):
                def check(start, end):
                    chars = [0] * 128
                    for i in range(start, end + 1):
                        c = s[i]
                        chars[ord(c)] += 1
                        if chars[ord(c)] > 1:
                            return False
                    return True

                n = len(s)

                res = 0
                for i in range(n):
                    for j in range(i, n):
                        if check(i, j):
                            res = max(res, j - i + 1)
                return res


        if __name__ == "__main__":
            # Your code goes here
            s = 'abcabcbb'
            print(lengthOfLongestSubstring(s))
            
 # Check if two String are Anagram
 
          s2 = "abcd"
          s1 = "adbc"

          if(sorted(s1) == sorted(s2)):
              print("The strings are anagrams.")
          else:
              print("The strings aren't anagrams."
              
 # Split a string of length N into string of width K
 
          some_string="lakmsldsmsdf sdksv"
          x=4
          res=[some_string[y-x:y] for y in range(x, len(some_string)+x,x)]
          print(res)
          
 # Given a matrix of m x n elements (m rows, n columns), return all elements of the matrix in spiral order.
 
         def spiralOrder(matrix):
            ret = []
            while matrix:
                ret += matrix.pop(0)
                if matrix and matrix[0]:
                    for row in matrix:
                        ret.append(row.pop())
                if matrix:
                    ret += matrix.pop()[::-1]
                if matrix and matrix[0]:
                    for row in matrix[::-1]:
                        ret.append(row.pop(0))
            return ret

        print(spiralOrder([
        [ 1, 2, 3 ],
        [ 4, 5, 6 ],
        [ 7, 8, 9 ]
        ]))
        <b> OUTPUT : [1,2,3,6,9,8,7,4,5] </b>
      
 # 
