# Python-Assignment-1
Majok Ali -BSCCS/2024/37636
a) Write a program to plot a line graph representing the temperature readings over a week: 20, 22, 19, 23, 21, 24, 20
import matplotlib.pyplot as plt

# Temperature readings for each day of the week
temperatures = [20, 22, 19, 23, 21, 24, 20]
days = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']

# Plotting the line graph
plt.plot(days, temperatures, marker='o', linestyle='-', color='blue')

# Adding labels and title
plt.title('Temperature Readings Over a Week')
plt.xlabel('Day')
plt.ylabel('Temperature (°C)')

# Displaying the graph
plt.grid(True)
plt.tight_layout()
plt.show()
b) Write a program to generate the arithmetic sequence starting at 5 with a common difference of 3, for 8 terms
# Define starting value, common difference, and number of terms
start = 5
difference = 3
terms = 8

# Generate the arithmetic sequence
sequence = [start + difference * i for i in range(terms)]

# Print the sequence
print("Arithmetic sequence:", sequence)
c) Write a program to calculate the volume under the surface z = x'+y'over the square region 0 ≤x,
from scipy.integrate import dblquad

# Define the function z = x^2 + y^2
def integrand(x, y):
    return x**2 + y**2

# Integration bounds: x from 0 to 1, y from 0 to 1
volume, error = dblquad(integrand, 0, 1, lambda x: 0, lambda x: 1)

# Print the result
print(f"Volume under the surface z = x^2 + y^2 over [0,1) x [0,1): {volume:.4f}")
🧮 Analytical Result:
You can also confirm this analytically:

∫
0
1
∫
0
1
(
x
2
+
y
2
)
 
d
x
 
d
y
=
∫
0
1
[
x
2
+
y
2
]
0
1
d
y
=
∫
0
1
(
1
+
y
2
)
d
y
=
[
y
+
y
3
3
]
0
1
=
1
+
1
3
=
4
3
∫ 
0
1
​	
 ∫ 
0
1
​	
 (x 
2
 +y 
2
 )dxdy
 The program should output:
 Volume under the surface z = x^2 + y^2 over [0,1) x [0,1): 1.3333
d) Explain the differences between compiled and interpreted programming languages, and classify Python in this context
| Feature            | **Compiled Languages**                                  | **Interpreted Languages**                                                 |
| ------------------ | ------------------------------------------------------- | ------------------------------------------------------------------------- |
| **Execution**      | Translated entirely into machine code before execution. | Translated line-by-line during execution.                                 |
| **Speed**          | Faster at runtime (after compilation).                  | Slower at runtime due to line-by-line interpretation.                     |
| **Error Handling** | Errors are shown after compilation (all at once).       | Errors show up as the program runs (line-by-line).                        |
| **Portability**    | Less portable; compiled code is platform-specific.      | More portable; source code can run anywhere the interpreter is available. |
| **Examples**       | C, C++, Rust, Go                                        | Python, JavaScript, Ruby                                                  |
🐍 Where Does Python Fit?
Python is generally considered an interpreted language, because:

It is not compiled directly to machine code.
It runs through an interpreter (e.g. CPython), which executes code line by line.
Errors are typically caught at runtime, not all in advance.
However, in practice, Python source code (.py files) is first compiled to bytecode (.pyc files), which is then interpreted by the Python Virtual Machine (PVM) — so it's partially compiled, but not to native machine code.

🔍 Summary:
Compiled: Entire code is converted to machine code before execution.
Interpreted: Code is executed line-by-line by an interpreter.
Python: Interpreted, though it compiles to bytecode internally.
