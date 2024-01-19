> [!art_title]
> 
> # Introduction to Set Theory

Several weeks ago, when I was talking about mathematics with a junior high school girl, I felt it is quite challenging to explain what functions are in a generalized sense without using the language of set theory. (Students in that age rarely know about set theory.) It is also difficult to explain why the variables of functions are not needed to be numbers, but also equations, functions, or something else. Finally, her mind was thoroughly bewildered by my chaotic explanations - I messed up.

## Why we need set theory?

Set theory was born with the idea of clarifying what we are talking about in mathematics, and once you capture the language of set theory, you can hardly bypass it. For example, in the language of set theory, functions can be explained as a special type of subsets of cartesian products; and such a cartesian products $X \times Y$ is not necessarily a set of ordered pairs of numbers, but anything we call elements in mathematics.

It also provide a rigorous way to distinguish predicates and the sets defined by the predicates in symbols. For example, the domain of the real function $f$ defined as $f(x) = \frac{1}{x}$ can be simply written as
$$
\mathrm{dom}_f = \{ x \in \mathbb R: x \ne 0 \}.
$$
As to the school girl, what she was taught in class is: the domain of $f$ is $x > 0$ or $x < 0$.is sufficient for most problems at her grade level, but it can lead to confusion in more abstract discussions.

Just like any mathematical theory that has survived to this day, set theory provide an easy path to explain mathematics unambiguously and explicitly; more than that, it provides a rigorous foundation of mathematics upon which specific mathematical problems and definitions can be generalized into the abstract realm. Although, we thereby discovered that our perplexity was even greater than before.

Certainly, the language system of set theory can easily engender dependency, but like many other mathematical theories, it is an abyss. Just like any mathematical theory that has survived to this day, set theory provide an easy path to explain mathematics unambiguously and explicitly. Thus, it provides a rigorous foundation of mathematics upon which some specific mathematical problems and definitions can be easily generalized into the abstract realm. But, we thereby discovered that our perplexity was even greater than before.

## Russell's paradox

Before 20th century, people (including me several years ago) tacitly accepted this statement as a truth: given a predicate $P(x)$ over elements, there must be a set $A$, such that $A = \{x: P(x)\}$. This was called the axiom of abstraction. This "axiom" appears to be in line with common sense, but it is erroneous.

In 1890s, George Cantor wrote to David Hilbert in a letter a paradox derived from the axiom of abstraction:

Let $P(x)$ be a predicate such that
$$
\forall x\; (P(x) \iff x \notin x).
$$
By the axiom of abstraction, there is a set
$$
R = \{x: P(x)\}.
$$
Then, either $R \in R$ or $R \notin R$. But, both of the cases are impossible. If $R \in R$, then $\neg P(R)$ implies $R \notin R$; if $R \notin R$, then $P(R)$ implies $R \in R$.

This contradiction shows that the naïve set theory admitting the axiom of abstraction is inconsistent. The same paradox is also discovered by Bertrand Russell several years later, and was presented in his 1903 book *The Principle of Mathematics*. This paradox has since become famous and is now known as **Russell's paradox**.

---

There are at least two ways two ways avoid Russell's paradox. One way is to introduce the concept of classes, and distinguish some classes from sets. As sets is a collections of elements, classes are collections of sets. In axiomatizations without ur-elements (those elements which are not sets), such as Von Neumann–Bernays–Gödel set theory (NBG) and Morse-Kelly set theory (MK), elements are also sets, so every set is a class.

Both in NBG and MK, every element is a set (only, in NBG, a set is not necessarily an element). So, by this implication, if a class $X$ is not a set, it can not be an element, in which case, we call $X$ a **proper class**.

In this sense, the axiom of abstraction is modified as:

> [!statement]
> 
> #### Schema of class comprehension
> 
> Given a predicate $P(x)$, then, there is a class
> $$
> X = \{ x: P(x) \land M(x) \},
> $$
> where the monadic predicate $M(x)$ is defined as "$x$ is a set."

In NBG, this is called the **class existence theorem**, which is a theorem derived from other NBG-axioms; in MK, on the other hand, this is accepted as the **axiom schema of class comprehension**.

In Russell's paradox, it is implicitly admitted that $x \in x$ is a predicate over sets. So, by the schema of class comprehension, the class, $R = \{x: x \in x\}$, does exist. Then, either $R$ is a set or not. If $R$ is a set, then either $R \in R$ or $R \notin R$. The paradox is encountered in both case. So, $R$ is not a set. In this case, $R$ is not an element, so $R \notin R$; but it dose not implies $R \in R$, as $R$ is not in the domain of the predicate, $x \in x$.

---

In some axiomatization, take Zermelo-Fraenkel set theory (ZF) for instance, sets are the only primitive objects, which means everything is a set. In this case, proper classes, as a type of non-set objects, are not formally acceptable. But, there is an axiom similar to the axiom schema of class comprehension:

> [!statement]
> 
> #### Axiom schema of specification
> 
> Given a predicate $P(x)$, for any set $A$, there is a subset $B$,
> 
> $$
> B = \{ x: P(x) \land x \in A \}.
> $$

Thus, as $x \notin x$ does not contain the subformula $x \in A$ for any set $A$, the structure $R = \{x: x \notin x\}$ does not necessarily exist in ZF. If $R$ exists in ZF however, it must be a set, and then Russell's paradox is encountered; so, $R$ does not exist in ZF.

## Choice of axioms

As to the answer to the question of whether there can be any set $x$ that satisfies $x \in x$, it depends on which axioms we invoke in the system. The mainstream of set theory does not accept $x \in x$ for any set $x$ based on the choice of axioms.

But, for mathematicians who believe in a different set of axioms, things might be different. In 1917, Dmitry Mirimanoff introduced a self-contained set, $x_0$, which, at a minimum, consists of only one element:


$$ x_0 = \left\{ \underbrace{\left\{ \underbrace{\left\{ \underbrace{\left\{ \cdots \right\}}_{x_3} \right\}}_{x_2} \right\}}_{x_1} \right\}. $$

Thus, for any natural number $i$, we always have $x_i = x_{i + 1}$, so $x_i \in x_i$.

Can we find a predicate $P(x)$ that can be written in first-order logic with the language of set theory such that $x_0 = \{ x : P(x) \land M(x) \}$ or $x_0 = \{ x : P(x) \land x \in A\}$ for some set $A$? If we cannot, does it contradicts the schema of class comprehension or the schema of specification? No. These two axioms do not state that a set or a class must be constructible in these ways. In other words, it is possible that some sets or classes are not constructible.

What I am trying to explain is: **a different choice of axioms may generates a different system**. As axioms always exist, no matter how we expand the theory, we can never be sure that an axiom might derives a paradox some day. So, we only believe in our axioms with the faith of our intuition.