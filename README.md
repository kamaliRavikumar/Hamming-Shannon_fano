EX 8: Huffman-Shannon_fano
```
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source.
```
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
```
Aim:
```
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source 
using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.
```

Tools Required:
```
. NumPy
. Matplotlib
. SciPy
```

Program:
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")

Calculation:
```
![Screenshot 2025-03-29 114142](https://github.com/user-attachments/assets/84ee5ba1-93ec-4ca8-8f1a-8b33ebafbcd1)
![shanonfano1](https://github.com/user-attachments/assets/cae4b657-8d13-481a-a632-f323566380d1)
![shanonfano2](https://github.com/user-attachments/assets/8425a988-cb0b-4c1d-a30f-79b05c2947b1)
![shanonfano3](https://github.com/user-attachments/assets/1a946a0f-0c7a-407b-94f0-4c18bd30d1f1)


Result:
```
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
