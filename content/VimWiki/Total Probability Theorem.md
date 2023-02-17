## Definition
Let *B1*, *B2*, *B3*,...*Bn* be [[partition in probability|partition]] of the sample space $\Omega$, that is:
	- $B_1 \cup B_2 \cup ... B_n = \Omega$
	- $B_i \cap B_j = \varnothing$

Then for any [[Event in Probability| event]] in $\Omega$,
$$P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2)...+P(A|B_n)P(B_n)$$
This is called **total probability theorem.

## Proof
$P(A) = P(A\cap \Omega)$, since $A = A \cap \Omega$.
Further, $$
\begin{align*}A\cap \Omega = A \cap( B_1 \cup B_2 \cup
B_n)\\ = (A \cap B_1) \cup (A\cap B_2) \cup (A \cap B_n) \end{align*}$$
Therefore,
$$ P(A) = P(A \cap B_1) + P(A \cap B_2) + P(A \cap B_n)$$
which 
 