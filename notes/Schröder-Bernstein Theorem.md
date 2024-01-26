

> [!art_title]
> 
> # Schröder-Bernstein Theorem

When I first attempted to prove the equinumerosity between $\mathcal P(\mathbb N)$ and $\mathbb R$, I realized that finding a bijection between these two sets was quite challenging if $\mathbb R$ is only defined as the set of all Dedekind cuts on the rational number line $(\mathbb Q, \le_{\mathbb Q})$ without introducing any digit system. Then I thought of a shortcut: if I could find two functions $f: \mathcal P(\mathbb N) \to \mathbb R$ and $g: \mathbb R \to \mathcal P(\mathbb N)$ being injective, then it might suffice to show that there exists a bijection between these two sets, i.e., they are equinumerous. This is actually a fact contained in the Schroeder-Bernstein theorem that is introduced in this article. However, like many theorems in set theory, it is intuitively acceptable, but at the time I neither knew about this theorem nor how to prove it.

## Statement and straight corollaries

> [!theorem]
> 
> #### Schröder-Bernstein Theorem
> 
> Let $A$ and $B$ be two sets such that $A \le_e B$ and $B \le_e A$. Then, $A \sim_e B$.

The converse of the theorem can be easily proved by the definition of $\sim_e$.

According to this theorem, equinumerosity between sets become simpler to be shown, such as the previously mentioned $\mathcal P(\mathbb N) \sim_e \mathbb R$. It also provides great convenience for defining cardinality in terms of ordinals. Moreover, according to this theorem, the relation $\le_e$ is an ordering on the universe $\mathscr U$, with $\sim_e$ being the equivalence relation associated with the ordering. That is,

1. $\le_e$ is reflexive: for any $x \in \mathscr U$, we have $x \le_e x$;
2. $\le_e$ is transitive: for any $x,y,z \in \mathscr U$, $x \le_e y \le_e z$ implies $x \le_e z$;
3. $\le_e$ is antisymmetric: for any $x,y \in \mathscr U$, $x \le_e y \le_e x$ implies $x \sim_e y$.

The reflexiveness and transitivity of $\le_e$ are corollaries of the definition of $\le_e$; and the antisymmetricity of $\le_e$ is precisely what Schröder-Bernstein Theorem states. (Note that, $\le_e$ is not hereby shown as a total relation on $\mathscr U$.)

Does Schroeder-Bernstein theorem rely on the axiom of choice? No, it does not, if it is stated in this form. Cantor first published this theorem in 1887 without any proof. In the following decades, Dedekind, Schröder, Bernstein, and others provided varies proofs of this theorem not relying on the axiom of choice. Below, I introduce what Robert André demonstrates in his book *Axioms and Set Theory*. It is surprisingly intuitive comparing with [Julius König's](https://en.wikipedia.org/wiki/Schr%C3%B6der%E2%80%93Bernstein_theorem#Proof).

## Proof

First, I demonstrate the proof outline.

Let $A$ and $B$ be two sets satisfying $A \le_e B$ and $B \le_e A$. Let $f: A \to B$ and $g: B \to A$ be two injection. Let $h = g \circ f: A \to A$.

In the following diagram, we can see that the composition $h$ maps the set $A$ onto its subset $h[A]$ with $h[A] \subseteq g[B] \subseteq A$.

> [!figure]
> 
> ![../_media/Cantor-Schröder–Bernstein theorem/proof-strategy.svg](../_media/Cantor-Schr%C3%B6der%E2%80%93Bernstein%20theorem/proof-strategy.svg)

Since $g$ is injective, we have $g[B] \sim_e B$. Since $f$ is also injective, so is their composition $h$. Thus, $h[A] \sim_e A$. Intuitively, it is acceptable that, as $g[B]$ satisfies $h[A] \subseteq g[B] \subseteq A$ and $h[A] \sim_e A$, it must be true that
$$
h[A] \sim_e g[B] \sim_e A.
$$
Then, by the transitivity of $\sim_e$, as $B \sim_e g[B]$, we have $B \sim_e A$. We proof this by the following lemma.

> [!lemma]
> 
> #### 
> 
> Let $X$ be a set, and let $f: X \to X$ be a injection. Then, for any set $Y$, if $f[X] \subseteq Y \subseteq X$, then $X \sim_e Y$.

**Proof.** Let $Y$ be a set with $f[X] \subseteq Y \subseteq X$. Since $f$ is injective, $X \sim_e f[X]$. As $f[X] \subseteq X$, either $f[X] = X$ or $f[X] \subset X$. If $f[X] = X$, then we have $X = Y$, which implies $X \sim_e Y$. Thus, assume $f[X] \subset X$. (In this case, $X$ is Dedekind infinite.)

As $f[X] \subseteq Y$, either $f[X] = Y$ or $f[X] \subset Y$. If $f[X] = Y$, then we have $Y \sim_e f[X] \sim_e X$ and hereby $Y \sim_e X$. So, assume $f[X] \subset Y$.

We are required to find a bijection $g: X \to Y$ in terms of $f$.

> [!figure]
> 
> ![../_media/Cantor-Schröder–Bernstein theorem/ring-in-proof.svg](../_media/Cantor-Schr%C3%B6der%E2%80%93Bernstein%20theorem/ring-in-proof.svg)

As $X \subseteq Y$, the complement $X \setminus Y$ is not empty. In the above diagram, we can set the $X \setminus Y$ forms a ring-like image in $X$, so is the images $f[X \setminus Y]$, $f^{1}[X \setminus Y]$, $f^{2}[X \setminus Y]$... 

Thus, we can find this sequence:

$$
\mathcal R = \left\{
\begin{aligned}
R_0 &= X \setminus Y, \\
R_1 &= f[R_0], \\
R_2 &= f[R_1], \\
R_3 &= f[R_2], \\
&\vdots
\end{aligned}
\right\} = \{ f^{i}[X \setminus Y] : i \in \mathbb N \}.
$$

It is easy to show that, for any $i \in I$, $f$ maps $R_{i}$ onto $R_{i + 1}$.

We define $g: X \to Y$ as
$$
g(x) =
\begin{cases}
f(x) &: x \in \bigcup \mathcal R; \\
x &: x \not \in \bigcup \mathcal R.
\end{cases}
$$
Now, it suffices to show that $g$ is the required bijection between $X$ and $Y$.

Let $y \in Y$. If $y \notin \bigcup \mathcal R$, then $g(y) = y$ by the definition of $g$. Assume $y \in \bigcup \mathcal R$. Then, there is an $i \in \mathbb N_{\ge 0}$ such that $y \in R_i$. As $f$ maps $R_{i - 1}$ *onto* $R_{i}$, there is an $x \in R_{i - 1}$ such that $f(x) = y$. Thus, $g$ is a surjection.

Let $x,y \in X$ satisfies $x \ne y$. Then, we only have the following cases:

1. $x,y \in \bigcup \mathcal R$;
2. $x,y \notin \bigcup \mathcal R$;
3. $x \in \bigcup \mathcal R$ and $y \notin \bigcup \mathcal R$.

In Case 1, as $f$ is an injection, we have $f(x) \ne f(y)$. In Case 2, $x \ne y$ implies $g(x) \ne g(y)$ by the definition of $g$. Assume Case 3. In this case, $f(x) \in \bigcup \mathcal R$. As $y = g(y) \notin \bigcup \mathcal R$, we have $g(x) \ne g(y)$. Thus, $g$ is an injection.

As $g$ is surjective and injective, it is a bijection from $X$ to $Y$.

$\blacksquare$

We embed this lemma into the proof outline, then the proof of Schröder-Bernstein Theorem is done.

## Can Schröder-Bernstein theorem be generalized to classes?

When I first proved the Schröder-Bernstein theorem, I actually encountered a problem, which is: according to the axiom of limitation of size in MK, a class $X$ is a proper class if and only if there exists an function $f:\mathscr U \to X$ being injective. Intuitively, I believed that in this case, there must be a function $b:\mathscr U \to X$ being bijection. However, to prove this claim, we need to generalize the Schröder-Bernstein theorem to any two classes which may not be sets. That is:

> [!statement]
> 
> For any classes $A$ and $B$ (whether or not they are sets), if $A \le_e B$ and $B \le_e A$, then $A \sim_e B$.

However, if we replace all instances of "set" in the above proof with "classes," then this proof would be invalid. Even if we avoid defining the sequence $\mathcal R$ and only say that for any $i \in \mathbb N$, $R_i$ is a class satisfying $R_i = f^i[X \setminus Y]$, we still have a problem: how can we set $\mathbb N$ as an index set for a sequence of classes $R_0, R_1, R_2, \ldots$ that some of them may be a proper class? Note that the existence of index classes is derived from the definition of functions, and is hereby relied on the axiom of class comprehension. If we say that a class $I$ indices some classes, $C_\alpha, C_\beta, C_\gamma,\ldots$, then this means that we acknowledge the existence of a function from $I$ to the collection $\mathcal C$ of $C_\alpha, C_\beta, C_\gamma,\ldots$. If there exists some $i \in I$ such that $C_i$ is not a set, then $\mathcal C$ cannot exist in our system. This is also why the union and intersection of any number of proper types cannot be defined.

Therefore, at least according to the above proof, we cannot generalize the Schröder-Bernstein theorem to classes. If we accept a more extensive "set theory" that allows proper classes as elements, or if we accept the axiom of choice and avoid constructing classes like $\mathcal R$ in the proof above, then this generalization would be much simpler - at least in these two cases, it is possible.

## Problems remained

- How to generalize Schröder-Bernstein theorem to classes in MK?