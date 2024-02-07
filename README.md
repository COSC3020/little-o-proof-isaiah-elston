[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/wM4-KOzy)
# Little-o

In addition to the big-O, big-$\Omega$, and big-$\Theta$ notation that
we covered at the beginning of this class, a few other notations are sometimes
used in asymptotic analysis.  For example, "little-$o$" notation.

Prove (i.e.\ give a formal mathematical proof) that $f(n)\in o(g(n))$ implies
that $f(n)\in O(g(n))$.

Hint: The proof will be *very* short and *very* easy. You can start by
identifying the differences between the definitions of O and o.

I have started with the formal definition of $o$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$f(n)\in o(g(n)) \iff \forall c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n)$

# Answer

First, I will reiterate the formal definition of big-$\mathrm{O}$ to help demonstrate the difference.

$$f(n) \in \mathrm{O}(g(n)) \iff \exists \ c > 0, \exists n_{0} > 0, \forall n \geq n_{0} : f(n) \leq cg(n)$$

Now, by cross-referencing the two mathematical definitions we can discern two key differences between big-$\mathrm{O}$ and little-$\mathrm{o}$... 

First of all, the positive constant $c$ is constrained differently between the two definitions. In big-$\mathrm{O}$, $c$ is constrained by $\exists$ which literally translates to "there exists" while $c$ is constrained by $\forall$ which literally means "for any" in the definition of little-$\mathrm{o}$. The distinction between the two is that $\exists$ is inherently a "looser" constraint in the fact that it only requires that a singular positive constant $c$ must exist to satisfy the defintion of big-$\mathrm{O}$. However, the $\forall$ constraint in little-$\mathrm{o}$ necessitates that **every** positive constant $c$ must satisfy the definition. It follows that if **every** positive constant $c$ must be valid to satisfy little-$\mathrm{o}$, then there is obviously **at least one** positive constant $c$ that will be valid to satisfy Big-$\mathrm{O}$. In summary, $\forall c > 0$ impliclty includes $\exists c >0$ by the very definition of $\forall$.

Next, little-$\mathrm{o}$ requires the function $f(n)$ to be **strictly less-than** *(<)* the function $cg(n)$. Meanwhile, Big-$\mathrm{O}$ requires that $f(n)$ be **less than or equal to** $cg(n)$ which is inherently a "looser" bound because the two functions are allowed to be equal in this case. Any case that where $f(n)$ is **strictly less-than** $cg(n)$ will **always** also satisfy any case where $f(n) \leq cg(n)$ by the definition's of $<$ and $\leq$. Much like $\forall$ and $\exists$ above, $\leq$ will always implicitly include $<$ whenever the elements being compared are consistent.

Thus, little-$\mathrm{o}$ has two logical operations that are **slightly** more strict than the ones in Big-$\mathrm{O}$ to the extent that the Big-$\mathrm{O}$ requirements will always be satisfied implicitly when satisfying the little-$\mathrm{o}$ requirements. Hence, $f(n) \in \mathrm{O}(g(n)) \implies f(n) \in \mathrm{o}(g(n))$.