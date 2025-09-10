
# EXP -02 Huffman-Shannon_fano
# NAME: Naveen K
# REG NO: 212223060184
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
python IDE with Numpy and Scipy.
# Program:
```
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
```
# Calculation:

<img width="457" height="354" alt="Screenshot 2025-09-10 130624" src="https://github.com/user-attachments/assets/30aaccd7-81b2-400b-9755-853ae9b0e9ae" />

# Output

![WhatsApp Image 2025-09-10 at 10 10 17 PM](https://github.com/user-attachments/assets/b1ef0c10-d9ed-40e2-91ca-71842e333fe2)
![WhatsApp Image 2025-09-10 at 10 10 18 PM](https://github.com/user-attachments/assets/061ef0ee-5e1f-4f74-ab7a-6768237a1197)
![WhatsApp Image 2025-09-10 at 10 10 22 PM](https://github.com/user-attachments/assets/ce4ad2bd-8b3a-4c39-acdb-b613b7056f83)
![WhatsApp Image 2025-09-10 at 10 10 26 PM](https://github.com/user-attachments/assets/a06e5f20-ba53-4927-be75-e6c4ff4aa5ae)



# Results:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

Average Codeword Length is : 2.625 

Entropy is : 2.625 

Efficiency is : 100.0 % 

Redudancy is : 0.0 

Variance is : 0.484
