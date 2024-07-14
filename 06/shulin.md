# CONS should not evaluate this arguments

I know one of the authors (friemdan) and what the cons function is, and I even understand lazy/call by need so I don't think that this paper will be REALLY bad, however given how the other papers have gone I'm probably wrong and I am fully prepared to not understand anything

Bro the "start" of this paper was actually another paper and I read it being a bit confused, I'm so cooked

"It builds suspensions of them" this sounds like thunks in Racket

[Subsumed](https://i.ytimg.com/vi/bXYNDTKA0aA/maxresdefault.jpg)

Convergence here refers to when we evaluate the arguments at cons when we need them, it'll be as if there wasn't a suspension anymore, the divergence is the fact that what's inside of a cons pair won't with this new calling convention
- Obviously one drawback will be when if these "suspensions" aren't pure functions then we won't get convergence

Space vs time moment
- This method gives us more time but uses more space, as well as adding some overhead to anything that implements it
- However, if we shove all of this into a compiler then that overhead shouldn't be a problem

Alright so thunks won't work with this definition of lists I belive, because you can only have atoms (which I believe are values) or lists in a list

...did this paper invent the "if" clause in Racket?

Strict functions evaluate its arguments then plop them into the function

Suspensions contain forms and environment, and when the suspension needs to be evaluated, the environment (which maps formals to their values) is used on the form

[Paper about call by need, look inside, call by name (I know I know he's getting there)](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ9YY78CrzfBqLeDgMc-AXW_JOzm2_waKi-rw&s)

Coercion: Unsuspending a suspension (e.g. evauluating a thunk)

CALC 2 JUMPSCARE INFINITE SERIES AAAA

BRO JUST MADE A STREAM [💀](https://www.youtube.com/watch?v=vcZRDvh3ddE) BRO MADE A GENERATOR FUNCTION [💀](https://www.youtube.com/watch?v=vcZRDvh3ddE) BRO USED THE YIELD KEYWORD IN C# [💀](https://www.youtube.com/watch?v=vcZRDvh3ddE)

This paper actually uses squares to end proofs which is nice because now I can skip over entire sections much easier
- Sorry but I'm going to only skim proofs, as they don't really help me out that much

Theorem 1 seems to be "ah yes my interpreter works"

Theorem 2 is the important one, it basically says "I do (cons "some value" $((\lambda (x) (x x)) (\lambda (x) (x x)))$) and then get the car of the list and be fine"

Theorem 3 is hard to understand due to the phrase "properly more powerful"
- I read the proof for this one, I don't understand the different between theorem 2 and theorem 3
- Just because you can do one feature that a call by value interpreter can't doesn't mean it's more "powerful"
    - See space vs time

This strong conjecture is meaningless to me because my brain isn't wrinkly enough

HE SAID THE WORD HE SAID LAZY CHAT CLIP THAT

Bro went from Theorem 3 "Mine is bigger than yours" to "The scheme for running suspensions described in the previous section is terribly impractical for a running interpreter"

This system is all well and good when you have pure functions, however there's a decent amount of stuff you can't do with pure functions
- See I/O [first result on Google](https://stackoverflow.com/questions/46721414/pure-functions-and-i-o)
    - ~~E.g. using a function like "get-temperature" that doesn't take in an argument will be tossed into a suspension, and then when coerced all instances will be replaced with the temperature at the first coercion~~
    - Observation 2 just threw this out the window, although the temperature will still be evaluated when coerced instead of when called

Call-by-delayed-value!!!!!

"Proof by it's obvious your honor" as a lowley undergrad yeah it's probably trivial

OH HE'S TALKING ABOUT I/O NOW EVERYONE BUCKLE UP

...wait streams existed before this paper? Whoops
- Note: Landin appearantly coined the concept

Guys I'm dumb I/O literally uses streams whoops I was wrong, it's just that you defenestrate the concept of pure functions, which at no point were mentioned in this paper

Theorem 5: We can do streams

Theorem 6: We can also do more than just streams 

Streams as coroutines are actually used by the Unity game engine

Variadic args mentioned

LISP does short circuiting for booleans nice

Friedman did the yanderedev style of if statements before it was cool

The conclusion says something to the effect of "if we only need to display the results, then we only need to evaluate what leads to the result being displayed"

What's interesting is this paper introduces "Lazy", but not "Call-by-need", where you'd use a box then when a function is coerced put the value into the box and if the same function gets coerced again just use what's in the box, so in effect this is truely our "Call-by-delayed-value"
- See observation 2, there's a reason we don't use/need boxes

This paper was honestly an easy read and everything flew by pretty quickly, I also think I understand most of what happened, which is really nice