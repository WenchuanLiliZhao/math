> [!art_title]
> 
> # Index of MK-axioms


> [!statement]
> 
> #### Axiom of extensionality
> 
> Two sets, $x$ and $y$, are identical, if they consist of exactly the same elements. In symbols,
> 
> $$
> \forall x\; \forall y\; \forall z ((z \in x \Leftrightarrow z \in y ) \implies x = y).
> $$


> [!statement]
> 
> #### Axiom schema of class comprehension
> 
> Given a predicate $\phi(x)$ written in first-order logic in terms of class and membership,
> 
> $$
> \exists A\; \forall x\; (x \in A \iff \phi(x) \land M(x)).
> $$


> [!statement]
> 
> #### Axiom of regularity
> 
> For any non-empty class $x$, there is an element $y \in x$ satisfying $x \cap y = \emptyset$.


> [!statement]
> 
> #### Axiom of paring
> 
> For any sets $x$ and $y$, the unordered pair $\{x,y\}$ is a set. In symbols,



> [!statement]
> 
> #### Axiom of limitation of size
> 
> For any proper class $C$, there is a function $f: \mathscr U \to C$ being injective.


> [!statement]
> 
> #### Axiom of power set
> 
> For any set $x$, the power $\mathcal P(x)$ is a set. In symbols,
> 
> $$
> \forall x\; \forall p\; ((M(x) \land \forall y\; (y \in p \iff y \subseteq x)) \implies M(p)).
> $$


> [!statement]
> 
> #### Axiom of union
> 
> For any set $x$, the union $\bigcup x$ is a set. In symbols,
> 
> $$
> \forall x\; \forall s\; ((M(x) \land \forall u\; (u \in s \iff \exists y\; (y \in x \land u \in y ))) \implies M(s)).
> $$


> [!statement]
> 
> #### Axiom of infinity
> 
> There is a set $I$ satisfying the following condition:
> 
> 1. $\emptyset \in I$;
> 2. $x^+ \in I$ for any $x \in I$.

