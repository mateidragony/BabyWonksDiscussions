# Call-by-name, call-by-value and the lambda-calculus

By G.D. Plotkin

## Introduction
- ISWIM Mentioned, massive win

I assume normal order reduction is the order in which you choose
to do beta-reduction.

Anyways, massive L for ISWIM is that it doesn't agree with the 
lambdaK-beta-delta

The paper wants a formal lambda_v for ISWIM, to show that it
isn't completely lame and useless

Then also they're gonna do a CBV ISWIM.

Finally use continuations to do CBV in CBN

## Technical Preliminaries
Lambda calculus, free nad bound variables

Substitution Prefix: [M/x]E => E with occurences of x swapped for M
[M/x]\(lambda x n) = (lambda x N);

Alphabetical equivalence relation. Basically comparing the DeBrujn
index versions.

## ISWIM

Unhinged

## the lambdaV calculus
Just restrict the beta rule.

Lots of proofs of stuff.


## Call-by-name

## Simulations and Translations
Show that the paradigms can simulate eachother.

### Simulate CBV using CBN
Useing continuations to make order of evaluation match

### Simulate CBN using CBV
```clojure
; So

#; ((λ (x) 2) (error "A"))

; Becomes
((λ (x)
   ((λ (x) (x (λ (x) (λ (x) (x 2)))))
    (λ (α)
      ((α (λ (x)
            ((λ (x) (x (λ (α) (error (α I)))))
             (λ (α) ((α (λ (x) (x "A"))) x)))))
       x))))
 (λ (x) x))
```

This took so much time and was not worth it. It is *kinda* cool
that it works though, and it helped me get better at parsing
lambda calculus.


## Personal Conclusions
This paper is f\*\*\* unhinged. I think that [this forum](http://lambda-the-ultimate.org/node/348) makes me feel better about my head
spinning as much as it did. The most important takeaway being
that we should look for PL/LC pairs to reason about semantics,
which allows us to see interesting things
