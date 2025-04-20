**Diophantine Equation:** A Diophantine equation is any equation where you're looking for integer solutions — typically for linear, quadratic, or polynomial expressions.
Most common form: ax + by = c, here (x, y belongs to z) this is the linear Diophantine equation for two variables. 

**When does it have a solution?**

The equation ax + by = c has integer solution if and only if gcd(a, b) | c. Meaning c is a multiple of gcd(a, b) or gcd(a, b) divides c without reminder. 

**Why?**

**Bézout's identity:** Because by bezout's identity, the set of all values of ax + by (for integer x, y) is exactly all multiples of gcd(a, b). So for the equation to be solvable, c must be one theose multiples. 

The equation of bezout's identity is ax + by = gcd(a, b) 
