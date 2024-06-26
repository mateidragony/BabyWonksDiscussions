
# A Theory of Type Polymorphism is Programming
### By Robin Milner

**Polymorphism:** having flexibility in types

Primitive polymorphic operators - it almost feels like arguing that polymorphism is the natural way of things.

The paper describes a method of gaining type flexibility, while still ensuring
robust programs.

Types are built from a set of basic types (int, bool, etc.), $\times$ (cartesian product), $+$ (disjoint sum), $\rightarrow$ (function), and `list`.

Polymorphic types are obtained by using *type variables* ($\alpha, \beta, \gamma, ...$).

Arbitrary types: ($\rho, \sigma, \tau$).


## Example 1: `map`
```clojure
(letrec ((map (lambda (f m)
            (if (null? m) 
                '() 
                (cons (f (car m)) (map (cdr m))))))))
```

Since the function map takes a function from things of one type to things of another type, we say it has type
$$((\alpha \rightarrow \beta) \times \alpha \text{ list}) \rightarrow \beta \text{ list}$$

How do we determine this from the bare declaration?
- We know the generic types of free identifiers (car, cdr, null?, '(), etc.)
- For each occurence of these variables, they must satisfy some requirements
- We can use `unify` to combine these requirements

For efficienct, the compiler should distinguish between differetn calls to `map` with
different monotypes.

## Example 2 `tagpair`
We want a function tagpair, such that `(tagpair a)` is a function under which 
$$(b . c) \vdash ((a . b) . (a . c))$$
```clojure
(define (tagpair a) 
    (lambda (b c)
        `((,a . ,b) . (,b . ,c))))
```
But we could define it differently

\* My guess is that `#` takes two functions and returs a function of two arguments that returns a pair with each function applied to each argument
```clojure
(define (pair a)
    (lambda (b)
        `(,a . ,b)))

(define tagpair
    (lambda (a)
        (let ((tag (pair a)))
            (tag # tag))))
```
1. $\alpha$ is assigned to a
2. pair($a$) acquires $\delta \rightarrow \alpha \times \delta$
3. This is used as the local generic type of tag
4. The tags are assigned
$\beta \rightarrow \alpha_1 \times \beta$ and
$\gamma \rightarrow \alpha_2 \times \gamma$
5. `#` is assigned an instance of its generic type
and the type equation for function application will
assign `(tag # tag)` the type
$\beta \times \gamma \rightarrow (\alpha_1 \times \beta) \times (\alpha_2 \times \gamma)$
6. tagpair acquires $\alpha \rightarrow (\beta \times \gamma \rightarrow (\alpha_1 \times \beta) \times (\alpha_2 \times \gamma))$

Something has gone wrong!

When instantiating the type of a variable bound by $let$
or $letrec$, only those type variables which don't occur in enclosing lambda-bindings may be instantiated.

In step 2 above, $\alpha$ is not generic, so when we get to 4, it stays as $\alpha$ instead of instantiating new instances.

So the rules for typing variables bound by $let$ and lambda are gonna be different!.

Example:
```clojure
(let ((I (lambda (x) x)))
    (I I))

((lambda (I) (I I)) 
    (lambda (x) x))
```
We could assign types to the former but not to the latter.


The lambda-abstraction may occur without an argument, creating an additional constraint

Consistent treatment of the nonglobal declaration
of a procedure that may contain a formal parameter of an enclosing procedure. This makes polymorphisming harder.

The `reversepair` limitation is interesting. I need to look back and see if they give an explanation of
why lambdas can't just always be treated like the lets.

Y combinator is very pogchamp!

## Section 3
Doing examples with a simple language, exp.

Why do types have to be directed?
Subtypes I guess?

### 3.2
This is just our interpreter, but also doing some type checking it looks like.
I also don't get why we have to do the $v | B_0$ things to convert to `true` or
`false`. I'm a bit confused by the distinction, esp. because the function D->V
is an injection.

### 3.4 Types and their semantics
Another question I have is what the turnstyle is doing for us?

The last example is wrong because it doesn't satisfy (ii) above.

https://stackoverflow.com/questions/12532552/what-part-of-hindley-milner-do-you-not-understand

These 2 propositions feel almost like gradual typing. Especially 1.
If a value is of some type, then it also counts as being of a type 
that is more specific than it. We can always make types more specific.

### 3.5 Type assignments
Type environment 🙌 🙌 🙌

Prefixed expressions - we're just listing out things in heirarchy.
We then use the pe to assign types.

A sub-pe is just a sub expression prefixed with the variable bindings
that enclose it.

A typing of a pe is an assignment of a type to each element of p,
and to each thing in e, so that the same type is assigned to
let x and e' in the expression `let x = e' in e`.
(Does not have to be a well typing yet)

`lambda y | (let f = (lambda (x) (xy)) in (fy))`

Typings are denoted with bars over things.

A typing is standard if for every typed sub-pe, the generic
type variables of each `let x_a` of the prefix occur nowhere
else in the pe `p' | d'`.

Well-typed:
- `p | x_t` is wt <=> standard and the type for the symbol is defined.
- `p | (e_a e_b)_t` is wt <=> `p|e` and `p|e'` are well typed, and `a = b->t`
- `p | (if e_a then e_b else e_b')_t` is wt <=> sub exp are all wt, `a=t_0` and `b=t`

I could keep going but this is just the stuff in our type checker.


Non Recursive notion of wt:
1. It is standard
2. For every (bound) occurrence `x_a` the corr. binding occurence has the same type
3. The conditions hold for all sub expressions (obvious things)

Talks about let polymorph again? 
`let I = (lambda (x) x) in ...` - We want `(Ie)` to have the same type as `e`
*but* 
`let I = (lambda (x) (let y = x in y)) in ...` - 

### 3.6 Substitutions
Map from type variables to types.

Prop 4: If $S$ invokes no generic variables of a wt, S(p | d) is
also well typed.

### 3.7 Well typed expressions do not go wrong
Relation bewteen semantic environments nad type environments.
env respects p  iff whenever `* x_p` is active if `p`,`env(x) : p`.

Semantic Soundess: If n respects `p`, and `p | d_T` is wt,
then evaluating the expression works.


## Part 4: A Well-Typing Algorithm and its Correctness
Based on unification, one of the parts of 311 that I barely understand.

## Part 5: Types in extended languages
1. We can do pairs, lists, and disjoint sums?
2. Assignments - Side effects make this hard to prove soundness. Cool!
3. Defining types at runtime
4. Multiple types for a procedure (but still not full poly) and coercions.

## Part 6: Conclusion
This was a good time, I'm glad that we read it. Soundness theorems go crazy
(i still haven't looked at them 💀)
