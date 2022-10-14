# Viet M. Bui
vietbui20@augustana.edu

# Homework 1
## 1.2
3.
$\Delta a_n = (N-a_n)a_n$ 
$a_{n+1} - a_n = (N-a_n)a_n$ 
$a_{n+1} = (N-a_n)a_n + a_n$ 

4. Let $a_n$ be the infected after n time
$\Delta a_n = (N-a_n)a_n$ 
$a_{n+1} - a_n = (N-a_n)a_n$ 
$a_{n+1} = (N-a_n)a_n + a_n$

1.3
1. a,e,f
a. $a_{n+1} = 3a_n, a_0 = 1$ 
	$a_n = 3^n(1)$ (Theorem 1)
	$a_n = 3^n$ 
e. $a_{n+1} = -a_n + 2, a_0 = -1$ 
	for the equilibrium value of the system we have $a = \frac{2}{1-(-1)} = \frac{2}{2} = 1$ (Theorem 2)
	$a_n = -1^nc + 1$ (for some constant c depends on the initial condition) (Theorem 3)
	Solving the equation with $a_0 = -1$:
	$a_0 = -1^0c + 1$
	$-1 = c + 1$
	$c = -2$ 
	In general,
	$a_n = -1^n(-2) + 1$ 
f. The equilibrium value for the dynamical system $a_{n+1} = 0.1a_n + 3.2, a_0 = 1.3$ is:
	$a = \frac{3.2}{1-0.1} \approx 3.556$  (Theorem 2)
	$a_n = 0.1^nc+3.556$ for some constant c depends on the initial condition, Theorem 3
	Solving for the equation with $a_0 = 1.3$:
	$1.3 = 0.1^0c+3.556$
	$c = -2.256$
	In general,
	$a_n = 0.1^n(-2.256) + 3.556$ 
	
2. a,e,j
a. $a = 0$ because b=0
|r|= 1.1 > 1 => unstable

e. $a_{n+1} = -1.2a_n + 50$
$a = \frac{50}{1+1.2} = 2.727$
|r |= 1.2 > 1 => unstable

f. $a_{n+1} = 1.2a_n - 50$
$a = \frac{-50}{1-1.2} = 250$ 
|r| = 1.2 > 1 => unstable

3. a,b,c (I did the wrong problem but I will just leave this section here. No. 4 is bellow this section)
a. $a_{n+1} = -1.2a_n + 50, a_0 = 1000$
![[Pasted image 20220922161850.png]]
$a = \frac{50}{1+1.2} = 22.73$
unstable

b. $a_{n+1} = 0.8a_n - 100, a_0 = 500$
![[Pasted image 20220922162102.png]]
$a = \frac{-100}{1-0.8} = -500$ 
stable

c. $a_{n+1} = 0.8a_n - 100, a_0 = -500$
$a = -500$
stable

4.
a. $a_{n+1} = -a_n + 2, a_0 = 1$
|n|$a_n$|
|-|-|
|0|1|
|1|1|
|2|1|
a of n remains the same 1
$a = \frac{2}{1+1} = 1$
The solution for the dynamical system
$a_k = -1^kc + 1$ 
=> $a_0 = -1^0c+1$ 
=>$1 = c + 1$
=>$c = 0$
=>$a_k = 1$

b. $a_{n+1} = a_n + 1, a_0=-1$
|n|$a_n$|
|-|-|
|0|-1|
|1|0|
|2|1|
|3|2|
|4|3|
a of n change 
because r = 1, and b = -1, no equilibrium value exist

c. $a_{n+1} = a_n + 3.2, a_0 = 1.3$
 |n|$a_n$|
 |-|-|
 |0|1.3|
 |1|4.5|
 |2|7.7|
 |3|10.9|
 There is not equilibrium value exist according to theorem 2

1.3 Projects
2. $a_{n+1} - a_n = k(M-a_n)(a_n -m)$ 
M = 5000
m = 100
k = 0.0001
a0 = 4000
=> $a_{n+1} - a_n = 0.0001(5000-a_n)(a_n-100)$$a_{n+1} = 0.0001(5000-a_n)(a_n-100)+a_n$
from this function we can find a range that $range(a_n) = (100, 5000)$ 
The model predict the population of the whales. If the range of an passed 5000 the capacity of the environment then the population will decrease and if the an less then 100 which is below the minimum survival then the population will also decrease. 

1.4
1. The equilibrium of the system (O,T) = (3000,4000)
![[Pasted image 20220923154952.png]]
a) with different coefficient 
|Cases| coef.1|coef.2 |coef.3|coef.4|
|-|-|-|-|-|
|Case 1| 0.6 | 0.3 | 0.4 | 0.7| 
|Case 2| 0.5 | 0.1 | 0.5 | 0.9|
|Case 3| 0.8 | 0.4 | 0.2 | 0.6|
| Case 4 | 0.1 | 0.7 | 0.9 | 0.3|
the starting values would be the 3000,4000
Case 1
![[Pasted image 20220923160314.png]]
Case 2
![[Pasted image 20220923160336.png]]
Case 3
![[Pasted image 20220923160357.png]]
Case 4
![[Pasted image 20220923160425.png]]
The system is very sensitive to the coefficient

b) with different starting values: The equilibrium value is stable and insensitive to the starting values
```python
import numpy as np
import matplotlib.pyplot as plt
# Here are the code i used for this part of the homework
# Initilize data
O0 = 2000
T0 = 5000

O = O0
T = T0

Oarr = np.array([O])
Tarr = np.array([T])

for i in range(1,8):
    Ob = 0.6*O
    Od = 0.3*T
    Tb = 0.4*O
    Td = 0.7*T
    O = Ob + Od
    T = Tb + Td
    print(O, T)
    Oarr = np.append(Oarr, [O])
    Tarr = np.append(Tarr, [T])
    
print(Tarr)
x = np.linspace(0, len(Oarr), len(Oarr))
plt.scatter(x, Oarr, marker = 'd', color='red')
plt.scatter(x, Tarr, marker = 's', color='blue')
plt.title("Graph")
plt.xlabel('Days')
plt.ylabel('Cars')
```
Case 1 (O,T) = (7000, 0)
![[Pasted image 20220923155255.png]]
Case 2 (O,T) = (5000,2000)
![[Pasted image 20220923155324.png]]
Case 3 (O,T) = (2000,5000)
![[Pasted image 20220923155445.png]]
Case 4 (O,T)= (0,7000)
![[Pasted image 20220923155511.png]]


4.
$M_{n+1} = 1.2M_n - 0.001O_nM_n$
$O_{n+1} = 0.7O_n + 0.002O_nM_n$ 
if we call the equilibrium values (M,O), then we must have $M = M_{n+1} = M_n$ and $O = O_{n+1} = O_n$ simultaneously. Substituting into the system yields:
$M = 1.2M - 0.001OM$
$O = 0.7O + 0.002OM$ 

$0 = 0.2M - 0.001OM = M(0.2 - 0.001O)$
$0 = -0.3O + 0.002OM = O(-0.30 + 0.002M)$

The first equation indicates there is no change in the mice population if M = 0 or O = 200.
The second equation indicates there is no change in the owl population if O = 0 or M = 150
Equilibrium exists at (O, M) = (0,0) and (O, M) = (150, 200) because neither population will change at those points.

a. In the example we can see clearly that the coefficients are 1.2, -0.001, 1.3, -0.002, the difference is the second coefficience is negative while in the problem the coefficient is positive. Why? because in the example problem, the owl population compete with the hawl population for surival which mean each can decrease each other population the negative coeffiecient indicates the reduction of population. In the problem, the mice could not harm the owl if their population increase but actually help to increase the population of the owl by providing food. 

b. 
Red for Owl
Blue for Mice
![[Pasted image 20220923003054.png]]
![[Pasted image 20220923003149.png]]
![[Pasted image 20220923003232.png]]
![[Pasted image 20220923003255.png]]
The system is insentive to the starting values, only when the population starting out really small like case 4 but the pattern is similar to other cases.

c. 
Case A (150, 200)
Same original coefficients
```python
Ob = 0.7*O
Od = 0.002*O*M
Mb = 1.2*M
Md = -0.001*O*M
O = Ob + Od
M = Mb + Md
```
![[Pasted image 20220923161428.png]]
with different coefficients
```python
Ob = 0.6*O
Od = 0.03*O*M
Mb = 0.2*M
Md = -0.001*O*M
O = Ob + Od
M = Mb + Md
```
![[Pasted image 20220923161530.png]]
Case B (150,300)
Original coefficients 
![[Pasted image 20220923191358.png]]
With modified coefficient like Case A above
![[Pasted image 20220923191428.png]]
Case C (100,200)
Original 
![[Pasted image 20220923191514.png]]
Modified like case A
![[Pasted image 20220923191554.png]]
Conclude that the system is sensitive to coefficient and insentive to initial values. 