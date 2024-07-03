# Towards a Theory of Type Structure
- Representation independence mentioned
- Big W for Polymorphism too
- We're gonna extend the lambda calculus, even though it's already perfect
- The weird ah upper-case lambdas are what let us bind type variables.
  - Using brackets for application to be quirky
- Notation try not to be impossible to understand, impossible challenge
  - The deltas denote an input type `t` and output type `w`
  - Example the type of $\Lambda t . \lambda x \varepsilon t . x$ is $\Delta t. t \rightarrow t$, because when we do $(\Lambda t . \lambda x \varepsilon t . x)[\text{Int}]$ we get an expression of type $\text{Int} \rightarrow \text{Int}$ for example.
- 
