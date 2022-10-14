Viet M. Bui
vietbui20@augustana.edu

# Theorem 2.1.5c

$\forall Q \in \mathbb{L}, \exists! X \in \mathbb{L}: Q+X = \bar{0}$
Proof: 
Define: $X = (-1)Q$ 
Define: $P = Q + X$
			$P = Q + (-1)Q$
			$(-1)P = (-1)(Q + (-1)Q)$
			$(-1)P = (-1)Q + (-1)((-1)Q)$ (axiom 5)
			$(-1)P = (-1)Q + (-1*-1)Q$ (axiom 3)
			$(-1)P = (-1)Q + (1)Q$ 
			$(-1)P = (-1 + 1)Q$ (axiom 4)
			$(-1)P = (0)Q$ 
			$(-1)P = \bar{0}$ (mean point zero) (axiom 7)
			Using axiom 7 where $aP = 0$ if and only if $a=0$ or $P = \bar{0}$ 
			since a in this case is not = 0 
			==> $P = \bar{0}$ 
			==> $P = Q + X = \bar{0}$
Assume X not unique
means $\exists Y \in \mathbb{L}: Y \neq X \land Q + Y = 0$ 
$Q + Y = \bar{0}$
$Q + Y = P$ (using the Define above)
==> $Q + Y = Q + X$
==> $(-1)Q + (Q + Y)= (-1)Q + (Q + X)$
==> $((-1)Q + Q) + Y = ((-1)Q + Q) + X$ (axiom 2)
==> $(Q + (-1)Q) + Y = (Q + (-1)Q) + X$ (axiom 1)
==> $\bar{0} + Y = \bar{0} + X$ (using the identity from top half of the proof)
==> $Y + \bar{0} = X + \bar{0}$ (axiom 1)
==> $Y = X$
Assumption falso
==> X is unique
