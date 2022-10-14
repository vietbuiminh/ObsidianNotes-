Viet Minh Bui
vietbui20@augustana.edu

# Theorem 2.6
Claim: $S \subseteq \mathbb{L} \wedge S \neq \emptyset => spanS$ smallest subspace of $\mathbb{L}$ containing $S$
Part I: 
Let $S = \{P_1, P_2, ... , P_n\}$ a linear combination, $spanS = \{t_1P_1 + t_2P_2 + ... + t_nP_n | t_i \in \mathbb{R} \}$ 
Assume $S \subseteq \wedge S \neq \emptyset$ 
W.M.S. spanS subspace $\mathbb{L}$
Let $Q_1, Q_2 \in spanS, l_i, r_i \in \mathbb{R}$
$Q_1 = l_1P_1 + l_2P_2 + ... + l_nP_n$
$Q_2 = r_1P_1 + r_2P_2 + ... + r_nP_n$
$Q_1 + Q_2 = (l_1P_1 + l_2P_2 + ... + l_nP_n) + (r_1P_1 + r_2P_2 + ... + r_nP_n)$
$Q_1 + Q_2 = l_1P_1 + r_1P_1 + l_2P_2 + r_2P_2 + ... + l_nP_n + r_nP_n$
$Q_1 + Q_2 = (l_1 + r_1)P_1 + (l_2 + r_2)P_2 + ... + (l_n + r_n)P_n$
since $l_i + r_i \in \mathbb{R}$, so $Q_1+ Q_2 \in spanS$
=> spanS closes under addition
Let $a \in \mathbb{R}$ $Q_3\in spanS, z_i \in \mathbb{R}$
$Q_3 = z_1P_1 + z_2P_2 + ... +z_nP_n$
$aQ_3 = a(z_1P_1 + z_2P_2 + ... +z_nP_n)$ substitution
$= az_1P_1 + az_2P_2 + ... +az_nP_n$ (axiom 5)
$= (az_1)P_1 + (az_2)P_2 + ... +(az_n)P_n$ (axiom 3)
$a*z_i \in \mathbb{R}$ so $aQ_3 \in spanS$ 
=> spanS closed under scalar mult.
so by definition 2.5 spanS subspace of $\mathbb{L}$ 
Part II:
Let K subspace of L, S subset of K
K subspace L => K is closed under addition & scalar mult. and S subset K
=> all linear combinations of S in K
=> spanS subspace K