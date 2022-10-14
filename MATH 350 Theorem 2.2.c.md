Viet Minh Bui
vietbui20@augustana.edu

# Theorem 2.2.5c
Claim: $\forall P \in \mathbb{L}, Q \in \mathbb{L}, \exists! Y: P+Y=Q$ 
Proof:
Define: Y = Q + (-P) ($Y \in \mathbb{L}$ by the definition of the additive inverse and sum of 2 points)
$P+Y=P+(Q+(-P))$
$P+Y=(Q+(-P)) + P$ (axiom 1)
$P+Y=Q+((-P) + P)$ (axiom 2)
$P+Y=Q+(P+(-P))$ (axiom 1)
$P+Y= Q+\bar{0}$ (additive inverse, thm 2.1)
$P+Y=Q$ (axiom 6)
=> P + Y = Q
=> Y has desired property

Assume Y is not unique
Mean $\exists X: X \neq Y \wedge P + X = Q$ 
$P + X = Q$
$P + X = P + Y$ (from the first half of the proof)
$(-P) + (P + X) = (-P) + (P+Y)$
$(-P + P) + X = (-P + P) + Y$ (axiom 2)
$(P + (-P)) + X = (P + (-P)) + Y$ (axiom 1)
$\bar{0} + X = \bar{0} + Y$ (additive inverse)
$X+ \bar{0} = Y + \bar{0}$ (axiom 1)
$X = Y$ (axiom 6)
Assumption is flase, Y is unique
