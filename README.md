<h1>ExpNo 8 : Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python</h1> 
<h3>Name: STEVE NITTIN SYLUS          </h3>
<h3>Register Number: 212224040331 </h3>
<H3>Aim:</H3>
<p>
    To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python
</p>
<h3>Procedure:</h3>
Input and Output
<br>Input:
This algorithm will take three words.
<br> B A S E<br>
    B A L L<br>
           ----------<br># ExpNo 8: Solve Cryptarithmetic Problem, a CSP (Constraint Satisfaction Problem) using Python

### Name: STEVE NITTIN SYLUS

### Register Number: 212224040331

---

## Aim

To solve a **Cryptarithmetic Problem**, a **Constraint Satisfaction Problem (CSP)**, using Python.

---

## Procedure

### Input and Output

#### Input

The algorithm will take three words.

```text
    B A S E
    B A L L
  ---------
  G A M E S
```

#### Output

It will show which letter holds which number from **0–9**.

For this case:

```text
    B A S E        2 4 6 1
    B A L L        2 4 5 5
  ---------      ---------
  G A M E S        0 4 9 1 6
```

---

## Algorithm

For this problem, we define a node that contains a letter and its corresponding value.

### `isValid(nodeList, count, word1, word2, word3)`

**Input:**
A list of nodes, the number of elements in the node list, and three words.

**Output:**
`True` if the sum of the values of `word1` and `word2` is equal to the value of `word3`; otherwise, `False`.

### Algorithm Steps

1. Set `m := 1`.

2. Traverse each letter of `word1` from right to left.

3. Find the corresponding value of each letter in `nodeList`.

4. Calculate the numerical value of `word1`.

5. Multiply `m` by `10` for each successive digit position.

6. Repeat the same process for `word2`.

7. Repeat the same process for `word3`.

8. Check whether:

   ```text
   val1 + val2 = val3
   ```

9. If the equation is satisfied, return `True`.

10. Otherwise, return `False`.

---

## Program

```python
from itertools import permutations


def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm

        # Check for leading zeros
        if S == 0 or M == 0:
            continue

        # Calculate the numerical values
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y

        # Check the equation constraint
        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None


# Call the function
solution = solve_cryptarithmetic()

if solution:
    SEND, MORE, MONEY = solution

    print(f"SEND = {SEND}")
    print(f"MORE = {MORE}")
    print(f"MONEY = {MONEY}")
else:
    print("No solution found.")
```

---

## Sample Input and Output

### Input

```text
SEND + MORE = MONEY
```

### Output

```text
SEND = 9567
MORE = 1085
MONEY = 10652
```

The corresponding digit assignment is:

```text
S = 9
E = 5
N = 6
D = 7
M = 1
O = 0
R = 8
Y = 2
```

Therefore:

```text
    9 5 6 7
  + 1 0 8 5
  ---------
  1 0 6 5 2
```

---

## Output

![Cryptarithmetic Output](https://github.com/user-attachments/assets/a9f1c727-4ea7-4256-a585-554c2ed5a83b)

---

## Result

Thus, the **Cryptarithmetic Problem was successfully solved using Python**.

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

## Program:
```
from itertools import permutations

def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm

        # Check for leading zeros
        if S == 0 or M == 0:
            continue

        # Check the equation constraints
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y

        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None

# Call the function
solution = solve_cryptarithmetic()

if solution:
    SEND, MORE, MONEY = solution
    print(f'SEND = {SEND}')
    print(f'MORE = {MORE}')
    print(f'MONEY = {MONEY}')
else:
    print("No solution found.")
```

<h2>Sample Input and Output:</h2>
SEND = 9567<br>
MORE = 1085<br>
<hr>
MONEY = 10652<br>
<hr>

## Output:

<img width="460" height="205" alt="image" src="https://github.com/user-attachments/assets/a9f1c727-4ea7-4256-a585-554c2ed5a83b" />


<h2>Result:</h2>
<p> Thus a Cryptarithmetic Problem was solved using Python successfully</p>
