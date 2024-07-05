# Towards a Theory of Type Structure
- Representation independence mentioned
- Big W for Polymorphism too
- We're gonna extend the lambda calculus, even though it's already perfect
- The weird ah upper-case lambdas are what let us bind type variables.
  - Using brackets for application to be quirky
- Notation try not to be impossible to understand, impossible challenge
  - The deltas denote an input type `t` and output type `w`
  - Example the type of $\Lambda t . \lambda x \varepsilon t . x$ is $\Delta t. t \rightarrow t$, because when we do $(\Lambda t . \lambda x \varepsilon t . x)[\text{Int}]$ we get an expression of type $\text{Int} \rightarrow \text{Int}$ for example.
- This polymorphism allows for user defined types
	- Example being complex numbers. 

## Notational Prelims
- Bro is the one who draws his own $\implies$
- We Have: 
	- $S \times S'$ - Cartesian Product
	- $S \implies S'$ - Set of Functions
	- $S \rightarrow S'$ - Set of Continuous Functions
- [f|x|x'] - \y if y=x then x' esle f(y)


## Syntax
- Syntax is formalized based on the set $T$ of type variables and
the set $V$ of normal variables
- $W$, the set of type expressions is
	- t
	- $w_1 \rightarrow w_2$
	- $(\Delta t . w)$
- Type variables can also be free and bound
- Substitution is the bane of my existence
- Every normal expression has an explicit type
	- $R_{Qw}$ is the set of normal expressions where assigning
	the type $Q(x)$ to every normal variable makes the expression
	have type $w$
	- Formally:
		- if $x \in V$ then $x \in R_{QQ(x)}$
		- More bullshit that more or less makes sense
- By structural induction,$r\in R_{Qw}$ and $r \in R_{Qw'}$ implies $w=w'$. This is cool, and makes intuitive sense

## Semantics
- Bro is writing all of these bullshit symbols for no reason 
- What the actual fuck is B? The meaning of a type expression
	- A function from type expression to T => D => D
	- Where D is the class of all domains
	- A domain is just a poset
- This paper assumes we know a lot more about denotational semantics
than we do.
- Reading on it's something called the semantic function? 
- $B[t](D)=D(t)$, $D$ is a function of $T$,
- Something with continuous functions
- A normal expression produces a value given a type assignment and
value assignment (environment)
- Environment must agree with the type structure.
	- $r \in R_{Qw}$ only takes environments that map $x$ into
	$B[Q(x)](D)$, and $r$ must produce a member of the domain
	$B[w](D)$.
- 2 a b c d and e are the interpreter?

## Representations
The set of representations between 2 domains (rep(D, D')) is the
set of continuous function pairs

- Making $\Phi \cir \Psi = I_D$ would have been too easy I guess
- To my understanding the weird subset represents different
- I'M SO DUMB, $I_D$ is the identity automorphism, NOT \\ x . x!!!!
partial function evaluation?
- We can use the weird $\Pi$ to do the same thing for functions
from types to domains, instead of just domains.

## Representation Theorem
I think that this is saying evaluating with respect to D and e is
the same as wrt D' and e', as long as the representation is relevant

Doing a lot of crazy stuff to formulate it though


## Category Theory
Combining domains and representations creates a category.

Objects are the different domains, and the morphisms are the 
representations that let us move between them.

I agree with shulin's take on the Ackermann function at the end :D

## Further Remarks
Idek

Overall I liked this paper, it has the same wild and wacky stuff with
having to keep track of a bajillion sets and substitutions in your
head, but it didn't completely lose me once I slowed down and took
the time.
