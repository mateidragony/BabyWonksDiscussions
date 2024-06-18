# Matei's notes

## 1. Introduction
- This paper seems so hype I can't wait to dig in 😋
- PL paper from the 70s try not to mention ALGOL 60 challenge (difficulty level: impossible)
- ALGOL 68 🤯
    - Kinda wanna learn ALGOL for the memes now lol
- [Approach in EL1](https://dl.acm.org/doi/abs/10.1145/360980.360992)

## 2. Illustrations of the type discipline
- ISWIM MENTIONED ISWIM MENTIONED!!!!!!!!!
- cons my beloved 
    - hd $\equiv$ car
    - tl $\equiv$ cdr
- Polymorphic means your type is a variable that gets assigned right when you actually need to test it
- Definiendum = term being defined, definiens = the definition
- Functions can have different types when we call them differently
    - That's why we use polymorphic types that iclude generic types in the type definition
- Recursive occurences of a formal definition must have the same type
- Fuck implementation we all abstract here

<img src="image.png" width=300>

- The reason we give the two tags two seperate $\alpha$ is because since we use $let$ to define tag, we should assume that ... actually idk why there's two $\alpha$...
- If i have this right, when binding variables using $let$, we can only create new generic type variables when the variable is not bound by an enclosing $\lambda$
    - So what do they mean by "instantiated". Like they're saying that instantiation turned $\alpha$ into $\alpha_1$ and $\alpha_2$ when we used tag twice. But why would that happen in the first place? Wait no I think I got it. OHHHHHH I'm so smart. Its the thing where calling a fucntion different times can be called with different types and yield different types. So that's why you put in generic types for functions. But in the special case of let, sometimes you already have the type bound in your enclosed scope so you have to always use that variables type even when you are calling that function multiple times.
- No idea how to give an independent characterization of the class of programs that can be well typed in their system 💀. Whatever the fuck that means
- Wtf is that type equation for streams???
- Why is self-application ill typed?? Is bro gonna explain?
- $let F(f) = \lambda(a,b)\cdot(f(a),f(b))$ is not allowed since let prevents us from instantiating $f$ and it forces $a$ and $b$ to be the same type
- $let \text{ reversepair}=\lambda(x,y)\cdot(\text{reversepair}(x), \text{reversepair}(y))$ works since its not

## 3. A simple applicative language and its types

