# Limitation of Size

## How large is arbitrary large?

There is an intuitive way to distinguish if a class is a proper class or a set: If a class is as large as "arbitrarily large" in size, then it must be a proper class.

Since $\mathscr U$ is our universe, no class can be larger than $\mathscr U$, even for some seemingly larger classes, e.g., $\mathscr U \times \mathscr U \subseteq \mathscr U$. So, every class $C \ge_e \mathscr U$ must be arbitrary large.

For example, let $C$ be the class of all singletons in $\mathscr U$; i.e.,
$$
C = \{ x \in \mathscr U: \forall y,y'\; (y,y' \in x \implies y = y') \}.
$$
Then, $C \ge_e \mathscr U$, as there is a function
$$
f: \mathscr U \to C: x \mapsto \{x\}
$$
being injective.

It is uncertain whether there exists a proper class $C$ such that $C <_e \mathscr{U}$. Nonetheless, John von Neumann believed that such a class could not exist. Therefore, he proposed this as an axiom in his system, which was later included in NBG and MK.

> [!statement]
> 
> #### Axiom of limitation of size
> 
> A class $C$ is a proper class if and only if there is a function $f: \mathscr U \to C$ being injective.

## Axiom of power set and cartesian products

In the article, *[[Relations and Functions]]*, we derives the definition of Cartesian products from the axiom of pairing with the axiom schema of class comprehension and the axiom of extensionality. But, with these axioms, we can not sure that if $X \times Y$ is a set or not even if $X$ and $Y$ are. In this article, we show that, $X \times Y$ is a set if and only if $X$ and $Y$ are.

> [!statement]
> 
> #### Axiom of power set
> 
> $$
> \forall x\; \forall p\; ((M(x) \land \forall y\; (y \in p \iff y \subseteq x)) \implies M(p)).
> $$

Note that, the truth value axiom of power set does not rely on $M(y)$ in the clause. If $y$ is not a set, in which case $y \in p$ fails, the statement before $\Rightarrow$ is false. By the property of $\Rightarrow$, the whole statement of the axiom is true.

> [!definition]
> 
> #### 
> 
> Let $A$ be a set. The **power set** of $A$, denoted $\mathcal P(A)$, is defined as the set
> 
> $$
> \mathcal P(A) = \{ S \subseteq A \}.
> $$

In ZFC, the axiom of power set is a different statement:

> [!statement]
> 
> For any set $x$, there is a set $p = \mathcal P(x)$. In symbols,
> 
> $$
> \forall x\; \exists p\; \forall y \; (y \in p \iff y \subseteq x),
> $$
> 
> where each letter denotes a set. In the language of MK, this statement can be expressed as
> 
> $$
> \forall x\; (M(x) \implies \exists p\; (M(x) \land \forall y\; (y \in p \Leftrightarrow y \subseteq x))).
> $$

If we invoke the statement as the axiom of power set in our system, the axiom of paring is redundant, because it can be derived from the statement with the axiom of union.

1. By this statement, given a set $x$ and a subclass $s \subseteq x$, $s$ must be a set, since there is a $p = \mathcal P(x)$ such that $s \in \mathcal P(x)$. 
2. Then, given two sets $x$ and $y$, $\{x\}$ and $\{y\}$ must be sets, as $\{x\} \subseteq \mathcal P(x)$ and $\{y\} \subseteq \mathcal P(y)$. By the axiom of union, $\{x,y\} = \{x\} \cup \{y\}$ must be a set.

However, in MK, the axiom of power set is stated differently and irrelevant to the axiom of pairing.

> [!theorem]
> 
> #### Schema of specification
> 
> Let $P(x)$ be a predicate. Then, for any $A$, if $A$ is a class, then there is a set $B$, such that $B = \{x \in A : P(x)\}$.

This is an axiom in ZFC. If we use the term class, schema of specification states that: every subclass of any set is a set.

**Proof.** Suppose $A$ is a set, but $B \subseteq A$ is not. Then, there is a function $f: \mathscr U \to B$ being injective. Then, $f$ is injective from $\mathscr U$ to $A$, as $B \subseteq A$. Then, $A$ is not a set, contradicting the assumption that $A$ is a set.

$\blacksquare$

> [!theorem]
> 
> #### 
> 
> Let $A$ and $B$ be two classes. Then, $A \times B$ is a set if and only if $A$ and $B$ are sets.

**Proof.** Assume $A \times B$ is a set. Aiming for a contradiction, suppose either $A$ or $B$ is not a set. Assume $A$ is not a set. Let $f: \mathscr U \to A$ be an injection. Let $b \in B$ and let $g: \mathscr U \to \mathscr U$, be defined as
$$
g(x) = (f(x), b).
$$
As $g[\mathscr U] \subseteq A \times \{b\}$, $A \times \{b\}$ is a proper class. Thus, there is an injection $h: \mathscr U \to A \times B$ with $h[\mathscr U] \subseteq A \times \{b\}$. Thus, $A \times B$ is not a set, no matter if $B$ is a set or not, contradicting the condition we have.

On the other hand, assume $A$ and $B$ are sets. Then, by the axiom of power set and the axiom of union, $\mathcal P(\mathcal P (A \cup B))$ exists as a set. Let $a \in A$ and $b \in B$, then we have $(x,y) \in A \times B$. As $(x,y) = \{\{x\}, \{x,y\}\}$, we have $(x,y) \in \mathcal P(\mathcal P(A \cup B))$. Thus, $A \times B \subseteq \mathcal P(\mathcal P(A \cup B))$. By the schema of specification, $A \times B$ is a set.

$\blacksquare$


## Schema of replacement


> [!theorem]
> 
> #### Schema of replacement
> 
> Let $A$ be a class, and let $f: A \to \mathscr U$ be a function. Then, if $A$ is a set, then $f[A]$ is a set.

**Proof.** Assume $A$ is a set. Let $f: A \to \mathscr U$ be a function. Then, $f\restriction_{A \times f[A]}$ is a surjection. Let $g: f[A] \to \mathcal P(A)$ be defined as
$$
g(x) = f^{-1}[x].
$$
Then, we have $\bigcup g[f[A]] = A$.

Seeking a contradiction, suppose $f[A]$ is not a set. Then there is a function $h: \mathscr U \to f[A]$ being injective. Then, as $g$ is an injection, $g \circ h: \mathscr U \to \mathcal P(A)$ is also injective. Thus, $\mathcal P(A)$ is a proper class. By the axiom of power set, $A$ is not a set, contradicting the assumption we have.

$\blacksquare$

The schema of replacement also derives the schema of specification. It is not hard to prove, so I do not elaborate on this.

## Introduction to the axiom of choice

There are some important consequences derived from the limitation of size. Some of them are famously controversial.

> [!statement]
> 
> #### Axiom of choice
> 
> For any set $A$, if $\emptyset \notin A$, then there is a function $f: A \to \bigcup A$ satisfies $f(x) \in x$ for any $x \in A$.

The axiom of choice is a useful proposition in many cases, as it can simplify the proofs of many theorems, for examples, some theorems in general topology. However, some mathematicians prefer to avoid using it and instead prove theorems without invoking this axiom if it is possible. On one hand, indeed, sometimes, in order to prove a theorem, we need to verify the smallest axiomatized model relative to that theorem. In other words, we need to know the minimum number of axioms required to prove the theorem. On the other hand, the axiom of choice is controversial because its statement does not provide us with any method for finding the choice function $f$, but only asserts its existence.

But, some important branches of set theory rely on the axiom of choice. For example, for defining cardinal numbers (the classes representing the sizes of sets) as sets rather than proper classes, invoking the axiom of choice is inevitable, as it derives more fundamental concepts in which terms the class of all cardinal numbers is defined.

In MK, however, the axiom of choice is an axiom derived from the axiom of limitation of size, and it is hereby a theorem. In addition, the limitation of size also implies the existence of the global choice function.

> [!statement]
> 
> #### Axiom of global choice
> 
> There is a function $f: \mathscr U \setminus \{\emptyset\} \to \mathscr U \setminus \{\emptyset\}$ such that
> 
> $$
> \forall x\; (x \in \mathscr U \setminus \{\emptyset\} \implies f(x) \in x).
> $$

The usually form the axiom of choice can be derived from the axiom of global choice.

So, as the limitation of size derives such two propositions, does it means the consistency of MK rely on the axiom of choice? Yes, but we have an option. Consider this diagram:

$$
\text{LS}
\begin{cases}
\implies \text{AGC} \implies \text{AC} \\
\implies \text{SR} \implies \text{SS}
\end{cases}
$$

In this diagram LS denotes for the limitation of size, ACG denotes for the axiom of global choice, AC denotes for the axiom of choice, SR denotes for the schema of replacement, and SS denotes for the schema of specification.

If the axiom of choice fails, by the property of $\Rightarrow$, every proposition that can imply the axiom of choice fails. But, even if so, the schema of replacement still might hold, and we can accept it as an axiom.





