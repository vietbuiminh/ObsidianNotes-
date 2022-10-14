## Viet M. Bui 
### vietbui20@augustana.edu

# MATH 350 Theorem 1.3.6
Correction:
Claim: $\forall v,w \in \mathbb{R}^3, v \neq w \implies \exists S \subseteq \mathbb{R}^3: v \in S \land w \in S \land S$ describes a line thru v and w

Proof:
Given $v = (v_1,v_2,v_3)$, $w = (w_1,w_2,w_3) \in \mathbb{R}^3$
Define: $S = \{(v_1,v_2,v_3) + t(w_1-v_1,w_2-v_2,w_3-v_3) | t \in \mathbb{R}\}$ 
$S \subseteq \mathbb{R}^3$ 
By definition of $w-v$, $w-v \in \mathbb{R}^3$ 
By definition of scalar multiplication, $t(w-v) \in \mathbb{R}^3$ 
By definition of vector addition, $v+(w-v) \in \mathbb{R}^3$ 
Conclude, $\forall x \in \mathbb{R}^3, x \in S \implies x \in \mathbb{R}^3$ 
when t = 0, the resulting vector of S = v
when t = 1, the resulting vector of S = w

Let $P \in S$, show $P$ on line thru v,w
$P = v + t(w-v)$ for some $t \in \mathbb{R}$
$w-v \neq 0$ ($w \neq v$)
$t \in \mathbb{R}$
$t(w-v)$ scalar multiple
P starts at v moves some distance t(w-v) in same/opposite direction.
==> P on the line thru v,w
Let Q on the line show Q in S
line thru v, w => line has direction $\vec{w} - \vec{v}$ 
Q is on the line which means
Q = v + k(w-v) for some k $\in \mathbb{R}$ 
=> $Q \in S$ 
==> P = Q (both set are in S)
There exist set S in $\mathbb{R}^3$ such that $v \in S \land w \in S \land S$ describes a line thru v and w.