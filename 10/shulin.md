# PLEASE JUT ONE MORE CALCULUS PLEASE GUYS JUST ONE MORE PLSSSS AH PAPER

## OH BOY WILL I EVEN UNDERSTAND THE INTRODUCTION???

"Does the language of the sequent calculus have merit as a practical compiler intermediate language, in the same way that the λ-calculus does?"
- I know that it has merit as an interpreted language from my coursework
- We've also seen this used in [ParentheC](https://bernsteinbear.com/assets/img/parenthec.pdf)
- I read a blogpost about a toy compiler that tried to use CPS (which is afaik is kind of the sequent calculus but not really) to translate to three address notation but idk man

System F omega mentioned
- When my professor explained System F we kind of got it
- He went on a tanget about System F omega and I was so lost

"The proof of the pudding is in the eating" 🔥

Why are kinds appearing I'm scared

## Sequent Core

IS THAT FUCKING $\mu \alpha.\tau$????
- It thankfully isn't but instead a continuation binding :O

CEK mentioned :D

Why are there square brackets around the type variable?

This notation is honestly similar to like reverse polish notation and I kind of dig it

I think this paper is heading in the direction of translating from Core to Sequent Core

K combinator mentioned

It looks like $\mu$ret is how we coerce the function stack things in lazy Core?
- It's like saying "HEY DO THIS RIGHT NOW BEFORE WE DO THE OTHER STUFF"
- I assume that the compiler will figure out where to put $\mu$ret stuff or use $\mu$ in some way

I guess we hate curried functions now and are doing multi-input functions 🗿
- The reasoning for why we need these went over my head :(

WHY IS THERE A STAR???
- Oh wait is this just like "ty" or "type"?

WHY IS $\DELTA$ THE LIST OF CONTINUATION BINDINGS AND NOT THE SYSTEM F THING WHEN WE'RE IN SYSTEM F? I'm 100% GOING TO CONFUSE THIS GOING FORWARD

I thought the operational semantics would make this amke more sense but I'm still a bit lost as too what is going on
- I dont know what $W \in W \ H \ N \ F$ means...

Figure 3 looks complicated so I'll just refer to it as I need it instead of trying to understand it 
- I've seen the heap stuff one other time and that other time was at a PhD defense 💀

I do not understand what proposition 1 is trying to say

Delta looks like the logical relation $\rho$ candidate stuff

HOLY FUCKING FIGURE 4 AND 5 JUMPSCARE

Okay so figure 4 makes sense IF I have wave away one thing that I think comes from System F omega

What the fuck are the logical rules in figure 5

"It may seem a bit bizarre that the polymorphism is pronounced “exists” instead of “forall” FINALLY SOMEONE ELSE WHO HAD THIS ISSUE THANK YOU!!!!

I feel like in order to understand this paper I need to know how the sequence calculus works and I don't...

PROGRESS AND PRESERVATION MENTIONED RAAAAAAAAAAAAAAAAAAAAH

## Translating aka I CALLED IT
Did Amr normal form just get mentioned?

We the continuation the same way we in compilers shrank if statements

This seems like a lot of talk for something that naively seems simple and was done in our Programming Languages class...

Wait wait why are we doing round trips?

## Section 4: I'M GENUINELY LOST
I don't speak Haskell so idk what to say

Okay so the reason this looks like what we did in Programming Languages is because it takes a page out of ANF's book

Tl;dr: We use join points aka we no longer get tail calls

# Section 5: AAAAAAAAAA
This sections seems to concern avoiding code duplication and is the first time we see a legitimate optimization in my opinion. The caveat doesn't seem to matter too much (parametricity :O) but still.

## Section 6: More understandable work
Basically a lot of this section basically seems to be "PLEASE USE OUR WORK AND NOT CPS". I am particularly irked by this paper saying that using CPS would leave us in "unmarked territory" while simutaneously talking about unmarked territory.

"the flat structure of SSA may be more convenient for representing imperative programs wherein block layout is more natural and higher-order features are not used" 
- Theorists upon discovering they made yet another language no one is going to use:
- SSA is still used today and I don't see it going away for a LONG time given that LLVM uses it

## Section 7: PLEASE USE SEQUENCE CORE AS YOUR IR PLEASE PLEASE
SSA is missing because it would sweep

## My conclusion
Maybe I'm just not functional pilled enough, but I still don't see the use for this IR. It feel as if someone did a lot of research into this area only for no one to ever utilize it. ANF makes a LOT more sense than this, and in the world of pure theory that's all I care about because I'm not going to be using ANF or Sequence Core as an IR.

Googling "sequent core intermediate representation", I don't see anyone using this for their IR; however Googling "ANF intermediate representation" I see tons of results. I feel like I read a paper that overcomplicated everything only to produce no meaningful results.