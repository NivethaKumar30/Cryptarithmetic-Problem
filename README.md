<h1>ExpNo 8 : Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python</h1> 
<h2>Name: NIVETHA.K </h2>
<h2>Register Number:  212222230102 </h2>
<H1>Aim:</H1>
<p>
    To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python
</p>
<h1>Procedure:</h1>
Input and Output
<br>Input:
This algorithm will take three words.
<br> B A S E<br>
    B A L L<br>
           ----------<br>
           G A M E S<br>

Output:
It will show which letter holds which number from 0 – 9.
For this case it is like this.

              B A S E                         2 4 6 1
              B A L L                         2 4 5 5
             ---------                       ---------
            G A M E S                       0 4 9 1 6
Algorithm
For this problem, we will define a node, which contains a letter and its corresponding values.<br>

isValid(nodeList, count, word1, word2, word3)<br>

Input − A list of nodes, the number of elements in the node list and three words.<br>

Output − True if the sum of the value for word1 and word2 is same as word3 value.<br>

Begin<br>
   m := 1<br>
   for each letter i from right to left of word1, do<br>
      ch := word1[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>
      val1 := val1 + (m * nodeList[j].value)<br>
      m := m * 10<br>
   done<br>

   m := 1<br>
   for each letter i from right to left of word2, do<br>
      ch := word2[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val2 := val2 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   m := 1<br>
   for each letter i from right to left of word3, do<br>
      ch := word3[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val3 := val3 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   if val3 = (val1 + val2), then<br>
      return true<br>
   return false<br>
End<br>
<hr>
<h1>Sample Input and Output:</h1>
SEND = 9567<br>
MORE = 1085<br>
<hr>
MONEY = 10652<br>
<hr>

<h1>Program:</h1>
<pre>
<code>
from itertools import permutations
def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm
        if S == 0 or M == 0:
            continue
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y
        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY
    return None
solution = solve_cryptarithmetic()
if solution:
    SEND, MORE, MONEY = solution
    print(f'SEND = {SEND}')
    print(f'MORE = {MORE}')
    print(f'MONEY = {MONEY}')
else:
    print("No solution found.")
</code>
</pre>
<h1>Output:</h1>

![image](https://github.com/user-attachments/assets/8a8149c0-d146-473b-b156-b5cf23088e35)

![image](https://github.com/user-attachments/assets/d9a80f7a-e88d-4450-a6e7-63992ca280ea)


<h1>Result:</h1>
<p> Thus a Cryptarithmetic Problem was solved using Python successfully</p>
