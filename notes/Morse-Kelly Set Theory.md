> [!art_title]
> 
> # Morse-Kelly Set Theory

There are more than one axiomatizations of set theory. The most famous one might be Zermelo-Fraenkel set theory with the axiom of choice (ZFC). But, due to ZFC's exclusion of proper classes, the formal descriptions of many things become convoluted. So, in this blog, we invoke **Morse-Kelly set theory** (**MK**), which is a proper expansion of ZFC.

## Primitive notions in MK

In MK, there are only two primitive notions: **class** and **membership**.

Intuitively, a class is a collection of objects. But, as classes are the only primitive objects in MK, a class is a collection of classes. Every letters, $x$, $y$, $z$, $X$, $Y$, $Z$, ... but $M$, denotes a class.

Membership, denoted by $\in$, is a relation between classes. The notation $x \in y$ means $x$ is an **element** or a **member** of $y$.

**Set**, however, is not a primitive notion in MK. Instead, we define the monadic predicate $M(x)$ as
$$
\forall x \; (M(x) \iff \exists y\; (x \in y)),
$$
and call every class $x$ satisfying $M(x)$ as a **set**. So, in MK, element and set is a pair of equivalent concepts. In this sense, set is a definable concept in MK. This may not be a reassuring answer, but it is true.

In any theory $T$, for define a term $t$, we must show that the objects or relation $[t]$ indicated by $t$ exists in $T$; otherwise, $t$ is undefinable. So, 

$$
t \text{ is defined in } T \implies [t] \text{ exists in } T.
$$

If $t$ is a primitive notion, then $t$ is not only defined, but also **assumed as defined** - only its explicit definition does not exist in $T$. In this case, the existence of $[t]$ cannot be proven in $T$, but assumed to be true; otherwise, $t$ is a primitive notion indicates objects does not exist in $T$. This is paradoxical.

For this reason, in MK, the existence of classes and membership are assumed; they are "axioms" without explicit statement in the theory. Thus, the existence of elements is a straight consequence of the set of primitive notions. And, as terms, element and set, indicate the same objects, set is defined as element.

> [!definition]
> 
> #### Sets
> 
> A class $x$ is a **set** if and only if it is an element, i.e., $M(x)$.

> [!note]
> This is one point where MK differs from NBG. In NBG, $M(x)$ serves as a similar but different predicate:
> $$
> M(x) \iff x \text{ is a set},
> $$
> but it does not implies $x$ must be an element. Gödel only accept the axiom
> $$
> \forall x\; ((\exists y \; (x \in y)) \implies M(x)),
> $$
> but not the converse. In this case, set has to be a primitive notion.

Those classes which are not set are called **proper class**. But, note that we can define proper classes so far, because the necessary axiom is not introduced yet.

## Fundamental properties of classes

There are eight axioms in MK (see [[../appendix/Index of MK-Axioms|Index of MK-Axioms]]). Each of them, we'll see, is independent from others. This is why I personally prefer to MK rather than some versions of ZFC (for example, the version on [Wikipedia](https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory)). In this chapter, I introduce three of MK-axioms, which represents the fundamental idea of the axiomatization of set theory.

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

> [!note]
> 
> In the following discussion, we simply say "predicate" rather than "predicate written in first-order logic in terms of class and membership" to reduce the length of text, if confusions are not alike in the context, unless this property needs to be emphasized.

Class comprehension is the only axiom schema in MK-axiom. Here is a simple word of why it is called an axiom schema. Once a statement is called a schema, it actually includes arbitrarily many statements in the same pattern. Take axiom schema of class comprehension for example. If our language is restricted in the first-order logic, this axiom cannot be completely described, as the expression $\forall \phi(x)$ is not allowed in first-order logic. So, in the formal expression, $\phi(\cdot)$ serves as a placeholder for predicates.

Class-builder notation, namely, describing set in the form $A = \{x: P(x)\}$, is a useful tool to reduce the length of discussion. This notation is straightforwardly derived from the axiom schema of class comprehension with the axiom of extensionality.

> [!definition]
> 
> #### Class-builder notation
> 
> Let $P(x)$ be a predicate over sets; i.e., $P(x)$ holds only if $M(x)$.
> 
> We write
> $$
> A = \{ x : P(x) \}
> $$
> if and only if
> $$
> \forall x\; (x \in A \iff P(x)).
> $$
> 
> In this case we write
> $$
> A = \{x,y,z, \ldots\}
> $$
> If and only if
> $$
> \forall u \; (P(u) \iff (u = x \lor u = y \lor u = z) ).
> $$

By the axiom schema of class comprehension, there is a class $R = \{x: x \notin x\land M(x)\}$, and it is a straight corollary that $R$ is not a set, i.e., $\neg M(x)$, for $M(R)$ raises Russell's paradox. So, in MK, proper class exist - at least, we have $R$.

> [!definition]
> 
> #### Proper classes
> 
> A class $x$ is a **proper class** if and only if it is not a set, i.e., $\neg M(x)$.

It is an interesting fact that, just as I mentioned in [[Introduction to Set Theory]], the axiom schema of class comprehension only gives predicates a chance to construct a class (by axiom of extensionality, this class is unique), but, it does not guarantee that every class $A$ can be written as $A = \{x: P(x)\}$. So, are there any indescribable class $A$? Neither MK, ZFC, nor NBG gives us an answer for this - it is unsure. So, it is note worthy that, when proving set theoretical theorems, we shall always avoid stating sentences like "(given an arbitrary class $A$,) let $P(x)$ be a predicate such that $A = \{x: P(x)\}$."

There are many definitions can be derived from the above two axioms:

1. **Subclass relation**, denoted by $\subseteq$;
2. **Arbitrary union**, namely, $\bigcup A$ whereas $A$ is a class;
3. **Arbitrary intersection**, namely, $\bigcap A$ where as $A$ is a class;
4. **Unordered pair**, namely, the class in the form of $\{x,y\}$ whereas $x$ and $y$ are sets;
5. **Empty class**, denoted by $\emptyset$, which can be obtained by $\emptyset = \{x: x \ne x\}$;
6. **Universal class**, or **universe**, $\mathscr U = \{x : M(x)\}$.

The above definitions are well-known, so I do not elaborate further here. However, there are several noteworthy facts related to these definitions.

1. The subclass relation is defined between two classes $x$ and $y$, and none of the axiom above guarantees that $x$ must be a set if $x \subseteq y$ with $M(y)$ - this is guaranteed by another MK-axiom.
2. The objects defined above are classes. None of the axioms above guarantees that any of them to be a set. Indeed, some of them are sets in MK, but they are guaranteed by other MK-axioms.

> [!definition]
> 
> #### Successors
> 
> Let $x$ be a set. The **successor** of $x$, denoted by $x^+$, is defined as the class
> 
> $$
> x^+ = x \cup \{x\}.
> $$

Similar to the definitions above, none of the axioms we have so far guarantees that $x^+$ must be a set. But, as a type of classes, this definition can be derived from the axiom of extensionality and the axiom schema of class comprehension:

Let $x$ be a set, then $\{x\} = \{y: y = x\}$ is a class. Let $P(u)$ be a predicate be defined as
$$
\forall u \; (P(u) \iff u \in x \lor u = x).
$$
Then, there is a class
$$
\{ u : u \in x \lor u = x \} = x \cup \{x\}.
$$
And, by the notation in the definition of successor, $x^+ = x \cup \{x\}$.

> [!statement]
> 
> #### Axiom of regularity
> 
> For any non-empty class $x$, there is an element $y \in x$ satisfying $x \cap y = \emptyset$.

It is a straight corollary that $x \notin x$ for any set $x$. Aiming for a contradiction, suppose there is a set $x \in x$. By the axiom schema of class comprehension, there is a class $\{x\} = \{u: u = x\}$, and $x \in \{x\}$ as $x = x$. As $x \in x$ and $x \in \{x\}$, we have $x \in x \cap \{x\}$. As $x$ is the only element in $\{x\}$, the axiom of regularity is contradicted.

A consequence of this is that the universe $\mathscr U = \{x: M(x)\}$ is a proper class. Because, if it is a set, then $M(\mathscr U)$ implies $\mathscr U \in \mathscr U$, contradicting the axiom of regularity.

Is it possible that $x \in x$ if $x$ is a proper class other than $\mathscr U$? In MK, this can be proven without invoking the axiom of regularity. Let $x$ be a proper class. If $x \in x$, then the property $M(x)$ is satisfied, contradicting the definition of proper class.

