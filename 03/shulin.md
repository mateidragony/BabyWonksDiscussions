No polymorphism 💀
- I realize now he meant overloading, whoops
- Overloading is covered, I am deeply confused by this statement

Monomorphic: Only existing in one form, opposite of polymorphic

"it is also convenient-particularly in on-line programming-to be able to leave out these specifications" I'd like to quickly talk about something I made once, and I'm going to assume that online programming means stuff like networking
* When I wrote my own RPC API, the biggest trouble that I had was with types, because everything was a method call onto an object, so I had to make a whole ass dictionary
* The solution I made ended up being ideal for the people who were using the API, but not so much so for the people creating it (me), as it quickly lead to a massively complex system with sub systems
* Now, this was probably a skill issue as everything ended up working out fine, but some reader might see this as relavent somehow

Well typed stuff will satisfy the Semantic Soundness Theorem (which I'm abreviating as SST), meaning that there won't be type errors at runtime
- Shoutout to Darshall for teaching us what this is

Types in Exp are "purely functional" so I'm sure later on we'll see Monads mentioned
"Operator application binding" oh my god he's gonna say the Monad word

ISWIM MENTIONED :O

$\alpha, \beta, \gamma$ are polymorphic types (polytypes)

$\rho, \sigma, \tau$ are just arbitrary types

This section basically uses a lot of big words to be like "hmmm yes we can solve for types"

To satisfy SST, it might be wise for a compiler to generate the different overloads at compile time

What the mackrel is (f # g)

In Exp, you can only fail by having a boolean evaluate to a non boolean value in a conditional, or have a "non functional value" try to be an operator in an application

What the scallop is happening in section 3

There seems to be some AST funkiness happenng, with like $\text{Env} = \text{I}d \to V$

Section 3 honestly seems to talk about some very specific stuff that only based PL nerds care about, but is ultimately fine to not completely understand

Okay I understand 3.3, each "functional value" comes bundled with a "type" and as long as each functional value is applied to the right type, we won't get "wrong", therefore we satisfy SST

Monotypes: a type that has no type variables, i.e. no generics (uses $\mu, v, \pi$)

Skipped 4 onto 5
