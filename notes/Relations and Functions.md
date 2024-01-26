> [!art_title]
> 
> # Relations and Functions
> 



Do you know the pigeonhole principle in elementary set theory? Let $P$ be a set with $n \in \mathbb N$ elements (pigeons) and $H$ be a set with $m \in \mathbb N$ elements (pigeonholes). Then, the following expressions are equivalent:

1. For any function $f: P \to H$, there are $p, p' \in P$ with $p \ne p'$ such that $f(p) = f(p') \in H$.
2. $n > m$.

In our axiomatization, sets are compared in terms of their size in a similar way. Before we delve into this topic, let's define some useful terms.

## Cartesian products

Cartesian products is a concept generalized from Cartesian coordinates systems by "throwing away" the their geometric properties. Given two classes $X$ and $Y$, the Cartesian product $X \times Y$ is the class of all possible ordered pairs $(x,y)$ whereas $x \in X$ and $y \in Y$. As classes are the only primitive objects in set theory, we must explain ordered pairs $(x,y)$ as classes.

There are ways to define ordered pairs as sets (see [*Ordered pair*](https://en.wikipedia.org/wiki/Ordered_pair#Kuratowski's_definition) on Wikipedia). In this blog, we introduce one of them.

In 1921, Kazimierz Kuratowski provide a way to define ordered pairs in the form of
$$
(x,y) = \{ \{x\}, \{x,y\} \}.
$$
Intuitively, $(x,y)$ must be a set, as it is quite a small class - it has only two elements.

> [!statement]
> 
> #### Axiom of paring
> 
> For any sets $x$ and $y$, the unordered pair $\{x,y\}$ is a set.

Thus, by the axiom of paring, as $x$ is a set, $\{x\} = \{x,x\}$ is also a set; similarly, $\{x,y\}$ is a set as $y$ is also a set. Thus, $(x,y) = \{ \{x\}, \{x,y\} \}$ is a set. Thus, ordered pairs and $n$-tuples can be defined.

> [!definition]
> 
> #### Kuratowski's formalization of ordered pairs
> 
> Let $x$ and $y$ be two sets. Then, the ordered pair $(x_1, x_2)$, is defined as the set
> 
> $$
> (x,y) = \{\{x\}, \{x,y\}\}.
> $$



If $X$ and $Y$ are classes, by the axiom schema of class comprehension, there exists a class
$$
C = \{ (x,y): x \in X \land y \in Y \}.
$$
This is where the definition of Cartesian product is derived from.

> [!definition]
> 
> #### Cartesian products
> 
> Let $X$ and $Y$ be two classes. The **Cartesian product** of $X$ and $Y$, denoted by $X \times Y$, is defined as the class,
> 
> $$
> X \times Y = \{ (x,y) : x \in X \land y \in Y \}.
> $$

What if $X$ and $Y$ are sets? Is $X \times Y$ also a set in this case? In ZFC, it is. And as MK is an expansion of ZFC, it is also true in MK. But, before proving this, we need to introduce some more axioms and define some concepts.

## Relations and functions

> [!definition]
> 
> #### Binary relations
> 
> Let $X$ and $Y$ be two classes. A class $R$ is a **binary relation**, or **relation**, on $X \times Y$ if and only if $R \subseteq X \times Y$. In this case, we write $xRy$ or $(x,y) \in R$.
> 
> Let $S$ be a subclass of $X$. The **image** of $S$ under $R$, denoted by $R[S]$, is defined as the class
> 
> $$
> R[S] = \{ y \in Y: xRy \land x \in S \}.
> $$
> 
> The **inverse** of $R$, denoted by $R^{-1}$, is defined as the class
> 
> $$
> R^{-1} = \{ (y,x): xRy \}.
> $$
> 
> We call $R[X]$ the **range** of $R$.
> 
> Let $T$ be a subclass of $Y$. The **pre-image** of $T$ under $R$ is defined as $R^{-1}[T]$.
> 
> The **domain** of $R$, denoted by $\mathrm{dom}_R$, is defined as the class,
> $$
> \mathrm{dom}_R = \{x: xRy\}.
> $$
> 
> We call $Y$ the **codomain** of $R$.

There is a straight corollary of this definition: $\mathrm{dom}_R = R^{-1}[Y]$.

> [!definition]
> 
> #### Functions
> 
> Let $X$ and $Y$ be two classes. A relation $f \subseteq X \times Y$ is a **function**, or a **mapping**, if and only if for any $x \in X$, there is at most one $y \in Y$, such that $y \in f[x]$. In this case, we write $y = f(x)$, and call $y$ the value of $f$ at $x$.
> 
> We write $f: X \to Y$ iff $\mathrm{dom}_f = X$. In this case, we say $f$ is a function from $X$ to $Y$.

Customarily, if $f(x) = y$ is a well-defined equation, we say that $f:X \to Y$ is defined as $f(x) = y$. Sometimes, this statement is also written as
$$
f: X \to Y : x \mapsto f(x).
$$

Note that, in the definitions above, Cartesian products, relations and functions are defined as classes, but not necessarily sets. Thus, in set theoretical axiomatization without proper classes, for example ZFC, function has to be defined in a different path, since we have to show that the existence of the Cartesian products $X \times Y$ does exists as a set whereas $X$ and $Y$ are sets in the first place.

## Comparing of sizes in terms of functions

Do you know the pigeonhole principle in elementary set theory? Let $P$ be a set with $n \in \mathbb N$ elements (pigeons) and $H$ be a set with $m \in \mathbb N$ elements (pigeonholes). Then, the following expressions are equivalent:

1. For any function $f: P \to H$, there are $p, p' \in P$ with $p \ne p'$ such that $f(p) = f(p') \in H$.
2. $n > m$.

In our axiomatization, sets are compared in terms of their size in a similar way. Before we delve into this topic, let's define some useful terms.

> [!definition]
> 
> ####
> 
> Let $X$ and $Y$ be two classes, and let $f: X \to Y$ be a function.
> 
> $f$ is **injective** (or a **injection**) if and only if for any $x, x' \in X$
> $$
> f(x) = f(x') \implies x = x'.
> $$
> 
> $f$ is **surjective** (or a **surjection**) if and only if for any $y \in Y$, there is an $x \in X$ such that $y = f(x)$.
> 
> $f$ is **bijective** (or a **bijection**) if and only if it is injective and surjective.

These terms are indeed well-defined in the system, considering the function $\imath: X \to X$ for a class $X$ be defined as $\imath(x): = x$.

> [!definition]
> 
> #### Equinumerous  classes
> 
> Let $X$ and $Y$ be two classes.
> 
> We write $X \le_e Y$ if and only if there is a function $f: X \to Y$ being injective.
> 
> $X$ and $Y$ are said to be **equinumerous**, denoted by $X \sim_e Y$, if and only if there is a function $f:X \to Y$ being bijective.
> 
> We write $X <_e Y$ if and only $X \le_e Y$ but $\neg(X \sim_e Y)$.

In a general sense, $X <_e Y$ means that $X$ is smaller than $Y$ in terms of size. In the example of the pigeonhole principle above, $P$ is larger than $H$ in size, as we have $P <_e H$. This is an example of comparing the sizes of finite sets.

However, the situation becomes more intriguing if both $X$ and $Y$ are infinite, where their sizes cannot be represented by any natural numbers. For example, $\mathbb N \sim_e \mathbb Q$ and $\mathbb N <_e \mathbb R$.

## Generalized the ordering on the universe

Editing...

