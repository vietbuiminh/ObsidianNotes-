Viet M. Bui
vietbui20@augustana.edu

# Theorem 2.7
Let: $S \subseteq \mathbb{L}$ in linear space
Claim: S is Linearly Independent <=>$\forall c_i \in \mathbb{R}, c_1P_1 + c_2P_2 + ... + c_nP_n = \bar{0}$ =>$\forall i, c_i = 0$ 
> Definition of Linearly Independent
>S L.I. $\forall a_i,b_i \in \mathbb{R}$
>$a_1P_1+a_2P_2+...+a_nP_n = b_1P_1 + b_2P_2 + ...+b_nP_n$
>=> $\forall i, a_i=b_i$

Part I:
Assume S is L.I.
	Assume $\forall c_i \in \mathbb{R}, c_1P_1 + c_2P_2 + ... + c_nP_n = \bar{0}$ 
	W.M.S. $\forall i, c_i = 0$
$c_1P_1 + c_2P_2 + ... + c_nP_n = \bar{0}$
$c_1P_1 + c_2P_2 + ... + c_nP_n = 0P_1 + 0P_2 + ... + 0P_n$ (axiom 6, 7)
=> $\forall i, c_i = 0$ (definition S in L.I.)

Part II:
Assume: $\forall c_i \in \mathbb{R}, c_1P_1 + c_2P_2 + ... + c_nP_n = \bar{0} => \forall i, c_i=0$
W.M.S. S is L.I.
	Assume $\forall a_i,b_i \in \mathbb{R}, a_1P_1 + a_2P_2 + ... + a_nP_n = b_1P_1+b_2P_2 + ... + b_nP_n$
	W.M.S. $\forall i, a_i=b_i$
$a_1P_1 + a_2P_2 + ... + a_nP_n = b_1P_1+b_2P_2 + ... + b_nP_n$
$(a_1P_1 - b_1P_1) + (a_2P_2 - b_2P_2) + ... + (a_nP_n - b_nP_n)= \bar{0}$ (additive inverse, axiom 2)
$(a_1 - b_1)P_1 + (a_2 - b_2)P_2 + ... + (a_n - b_n)P_n= \bar{0}$ (axiom 4)
$(a_1 - b_1)P_1 + (a_2 - b_2)P_2 + ... + (a_n - b_n)P_n = 0P_1 + 0P_2 + ... + 0P_n$ (axiom 6, 7 similar to partI)
=>$\forall i, a_i-b_i = 0$ 
=>$\forall i, a_i = b_i$
=> S is L.I.


