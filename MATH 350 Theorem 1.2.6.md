## Viet M. Bui 
### vietbui20@augustana.edu

# MATH 350 Theorem 1.2.6
Claim: $\forall \vec{v}=(v_1,v_2,v_3) \in \mathbb{R}^3, \exists! \vec{x} = (x_1,x_2,x_3) \in \mathbb{R}^3: \vec{x} + \vec{v} = (0,0,0)$  
Proof: 
(1) Assume: $\vec{x} \in \mathbb{R}^3$ 
			$\vec{x} = (-v_1, -v_2,-v_3)$  ($v_1,v_2,v_3 \in \mathbb{R}$)
			$\vec{v} + \vec{x} = (v_1 + (-v1), v_2 + (-v_2), v_3 + (-v_3))$ 
					$= (0,0,0)$ definition of vector sumation
(2) Assume $\vec{x}$ is not unique
	thus $\exists \vec{z} = (z_1,z_2,z_3) \in \mathbb{R}^3: \vec{v} + \vec{z} = 0$
	and $\vec{z} \neq \vec{x}$  
	      By vector addition, and add each vector to $\vec{v}$ to get the result as the origin (0,0,0):
	      $\begin{cases} \vec{v} + \vec{x} = (v_1+(-v_1),v_2+(-v_2),v_3+(-v_3)) = (0,0,0)\\ \vec{v} + \vec{z} = (v_1+z_1,v_2+z_2,v_3+z_3) = (0,0,0)\end{cases}$ 
	      ==> $\vec{v} + \vec{x} = \vec{v} + \vec{z}$ 
	      ==> $\vec{z} = (-v_1,-v_2,-v_3)$
	      ==>$\vec{x} = \vec{z} \Rightarrow\!\Leftarrow$ (contradict) 
	      $\vec{z}$ has to be the same with $\vec{x}$ to get the vector addition to be the origin.
Geometrically, vector x can be visualized as the opposite of vector v with direction pointing the opposite of vector v, and length is the same.

$\forall \vec{v}=(v_1,v_2,v_3) \in \mathbb{R}^3 \wedge \vec{w}=(w_1,w_2,w_3) \in \mathbb{R}^3, \exists! \vec{y} = (y_1,y_2,y_3) \in \mathbb{R}^3: \vec{y} + \vec{v} = \vec{w}$ 
Proof:
(1) Let: $v_1 = 0, v_2=1, v_3=2, w_1 = 2, w_2=1,w_3=0$ 
			$\vec{v} = (0,1,2) \wedge \vec{w} = (2,1,0)$ 
			$\vec{v} + \vec{y} = \vec{w}$ 
			using the definition of vector sum
			$\vec{y} = (2,0,2)$ (y exists)
(2) Let: $\vec{k} = (k_1,k_2,k_3) \in \mathbb{R}^3$ 
	means $\exists \vec{y} \neq \vec{k}: \vec{v} + \vec{y} = \vec{w} \wedge \vec{v} + \vec{k} = \vec{w}$ 
	      By vector addition, and add each vector to $\vec{v}$ to get the result as the vector w:
	      $\begin{cases} \vec{v} + \vec{y} = (v_1+y_1,v_2+y_2,v_3+y_3) = (w_1,w_2,w_3)\\ \vec{v} + \vec{k} = (v_1+k_1,v_2+k_2,v_3+k_3) = (w_1,w_2,w_3)\end{cases}$ 
	      ==> $\vec{v} + \vec{y} = \vec{v} + \vec{k}$ 
	      ==> $k_1=y_1,k_2=y_2,k_3=y_3$
	      ==> $\vec{k} = (y_1,y_2,y_3)$
	      ==>$\vec{y} = \vec{k} \Rightarrow\!\Leftarrow$ (contradict) 
	      $\vec{k}$ has to be the same with $\vec{y}$ to get the vector addition to be vector w.
Geometrically, vector y can be visualized as starting from the tip of vector v and ending with the tip of vector w.
			