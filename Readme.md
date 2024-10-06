Example: The velocity components in a two-dimensional flow of an inviscid fluid are. <br />
                                u = Kx / (x^2+z^2 ) <br />
                                w = Kz / (x^2+z^2 ) <br />
Is the flow nondivergent?
<br />

Solution: 
         
<pre>
import math            # library of python for calculate the calculation of below 
import sympy as sp     # library of python for calculate the calculation of below
import numpy as np     # library of python for calculate the calculation of below


  
 # If you want to calculate the gradient symbolic :
  
x, y, z, K = sp.symbols('x z K')              # Definition of symbolic variables

u = (K * x) / ((x**2) + (z**2))                 # Definition of functions
w = (K * z) / ((x**2) + (z**2))                  # Definition of functions

grad_u = sp.gradient(u, (x))              # Calculating the gradient symbolically
grad_w = sp.gradient(w, (z))              # Calculating the gradient symbolically

print("u:", grad_u)                             # Gradient display
print("w:", grad_w)                             # Gradient display

  

 # If you want to calculate the gradient numerically :
  
def u_num(x, z, K):
    return (K * x) / ((x**2) + (z**2))

def w_num(x, z, K):
    return (K * z) / ((x**2) + (z**2))

x0, z0, K0 = 1, 2, 3
grad_u_num = np.array(sp.gradient(u_num, (x, z))(x0, z0, K0))
grad_w_num = np.array(sp.gradient(w_num, (x, z))(x0, z0, K0))

print("u:", grad_u_num)
print("w:", grad_w_num)
