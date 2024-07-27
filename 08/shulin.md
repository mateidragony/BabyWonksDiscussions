# All my homies hate goto

Starting of by calling C a "higher level" langauage (it's not directly but it's funny to say it is)

"A programmers activity ends when he has constructd a correct program" [WRONG](https://www.youtube.com/watch?v=EhkQxkZ0G1s), WRITE COMMENTS PLEASE FOR THE LOVE OF GOD

Okay the parenthesis are starting to get as bad as parenthesis in Racket

"dynamic index" FRIEDMAN STARTED SCREAMING WHEN I READ THESE WORDS AND A ROCKET CRASHED HELP

Okay so here's my summary of the paper
- The text that a programmer writes is very static, however when the program runs it's very dynamic
- We want to make the program as static as possible as our feeble brains cannot comprehend dynamic programs that well
    - This point actually plays into why some people hate OOP
- We can have branching behavior without goto
- We can do loops without goto
- Doing goto to an arbritrary line makes it hard to describe the "progress" from where it's currently at
- Goto also violates reentrance

The main takeaway is that goto is too powerful, it lets you do a lot of stuff which gets REALLY confusing really fast 