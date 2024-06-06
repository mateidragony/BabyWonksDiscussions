# Calvin's thoughts
[link](http://sunnyday.mit.edu/16.355/Hoare-CACM-69.pdf)
[wikipedia](https://en.wikipedia.org/wiki/Hoare_logic)

This was a fun paper, and surprisingly easy to read.

Dr. Siek talked about proving programming correctness in 343 Data Structures,
though without mentioning Hoare specifically.

Most interesting to me is thinking about the role of the language implementer
in 'providing' (for lack of a better word) axioms for correctness in how they
choose to design the language. See for example the [Algol60 Standard](https://www.algol60.org/reports/algol60_rr.pdf?page=13).

I also felt that there was a strong connection between this paper and the book
*Godel, Escher, Bach*, wherein formal systems are discussed, vis-a-vis
typographical substitutions, as well as the chapter "BlooP and FlooP and GlooP"
which similarly relates programs to proofs.

I wonder in which cases it becomes useful to apply the formal system. As the
author states, "Once a powerful set of supplementary rules has been developed,
a 'formal proof' reduces to little more than an informal indication of how a
formal proof could be constructed." When reasoning about, for example, graph
algorithms in 403 Algorithm Analysis, proof of algorithm implementation was
ignored in comparison to high-level reasoning about what different operations
do to various data structures. I really like the idea of being a lot more
formal and nitpicky with respect to implementation correctness.

Something else interesting is the idea of a programming language in which
writing code also requires a proof of the code's correctness, i.e. providing
pre/post-conditions, loop invariants where needed, whatever else the compiler
couldn't infer. [Ada Contracts](https://learn.adacore.com/courses/intro-to-ada/chapters/contracts.html)
seem pretty close to what I have in mind in terms of embedding with a practical
language rather than something like Coq.

I also found [CompCert](https://compcert.org/) which is super cool. Darshal I
think mentioned this briefly in the meeting about gradual typing.

