# Experiment 2: Normal Distribution -employee wage analysis 

**Question:**

Write a Python program that, given the mean, standard deviation, and number of employees, 
estimates how many employees fall within: 
(a) a given range (between two values), 
(b) less than a given value, and 
(c) greater than a given value.

**AIM:**

To estimate the number of employees whose wages fall in a specified range, less than a value, 
or greater than a value, using the properties of the Normal distribution.

**SOFTWARE REQUIRED:**
 Python and Libraries - math

 **Mathematical Explanation**

 <img width="664" height="471" alt="image" src="https://github.com/user-attachments/assets/264edd11-a7e0-4c84-a916-1f924efaf79e" />

 **Steps in Python**
1. Import math for error function  
2. Define normal_cdf (x,mu,sigma) function to  compute Normal CDF. 
3. Take input values: mean, standard deviation, total employees and required wage limits.  
4. Compute probabilities using the formulas above and execute for output.

**PROGRAM**
```
import math 
 
# Normal CDF function 
def normal_cdf(x, mu, sigma): 
    return 0.5 * (1 + math.erf((x - mu) / (sigma * math.sqrt(2)))) 
 
# Input values 
mu = float(input("Enter mean (e.g. 200): ")) 
sigma = float(input("Enter standard deviation (e.g. 5): ")) 
n = int(input("Enter number of employees (e.g. 2000): ")) 
 
# Range case 
a = float(input("\nEnter lower limit (a): ")) 
b = float(input("Enter upper limit (b): ")) 
p_between = normal_cdf(b, mu, sigma) - normal_cdf(a, mu, sigma) 
num_between =p_between 
 
# Less than case 
x = float(input("\nEnter value for 'less than': ")) 
p_less = normal_cdf(x, mu, sigma) 
num_less = p_less 
 
# Greater than case 
y = float(input("\nEnter value for 'greater than': ")) 
p_greater = 1 - normal_cdf(y, mu, sigma) 
num_greater = p_greater 
 
# Results 
print("\nEstimated Results:") 
print(f"(a) Employees between {a} and {b}: {num_between:.4f}") 
print(f"(b) Employees less than {x}: {num_less:.4f}") 
print(f"(c) Employees greater than {y}: {num_greater:.4f}")
```
**OUTPUT:**

<img width="497" height="333" alt="image" src="https://github.com/user-attachments/assets/b430f321-522d-4696-9b14-9d66ee791833" />

**RESULT:**

The program successfully estimated the number of employees falling between two wage 
values, less than a value, and greater than a value, using the Normal distribution.
