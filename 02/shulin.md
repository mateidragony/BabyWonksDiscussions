# Shulin's notes

## Some notes about the author
Before I began reading the paper, I thought it'd be important to first lookup some background on the author, [Peter Landin](https://en.wikipedia.org/wiki/Peter_Landin), who has unfortuanatley since passed. According to Wikipedia (which I'm largly plagarizing in this section), he was the first of many to understand the importance of lambda calculus to PL, and he even collaborated with the legendary Djikstra to tutor students in the ALGOL programming language, with [one of those students](https://en.wikipedia.org/wiki/Tony_Hoare) being the one to develop the quicksort algorithm. He was also openly bisexual, and someone campaigned for gay rights.

## Paper

### 1. ISWIM, YouSWIM, we all SWIM for SWIMCREAM
The ISWIM language appears to draw from category, where you have objects and a way to describe how to go from one object to the next (morphism)

From my understanding, you first try to define the simplest elements then move up from that, and move up more 

I would like to add that I'm currently trying to get myself to continue reading a category theory book, hence me shoving it into my notes despite it probably not making any sense

Upon rereading the introduction for the 999ths time I've come to realize that the language instead is truely just describing things in terms of other thing, nothing more nothing less, and choosing whta to label as a "primitive" and say "fudge it it's obvious what this is"

### 2. What the Where?
The author goes full linguist and says some big words like "syntax" and "linguistic structure", but ulitmately just asks some questions on how a "where clause" is formulated

It's like this section is meant as a blueprint for formulating a language rather than an objective answer such as "this is the best eat dirt"

### 3. && vs &
I have no idea what ALGOL looks like, but I think this section is getting at concept vs implementation. ISWIM aims to do some tasks, so when talking ISWIM that can do these tasks we say "logical ISWIM", however as soon as we implement a language that does these tasks, e.g. ALGOL 60, we call that "physical ISWIM". "Reference ISWIM" is just what the report uses, and is an alias for "reference ALGOL 60" I think???


### 4. I wish I read this section before writing notes on the last

Alright four levels here we go

1. Implementation
2. Concepts and Grammar
3. Concepts
4. Actual "Code"

### 5. There is so much vocabulary
Someone make a quizlet oh my god

* amessage: either a definition OR a demand that has an aexpression as its body (e.g. print(your mother))

I'm not putting the rest, just look at the examples they're designed to be obvious

### 6. Wake up Friedman
This section talks about stuff I've never seen in my life, whelp

My main takeaway is that ISWIM is a weirder version of Racket


### 7. I actually don't know what's going on
💀

I'm sorry there's too many picture lookin' things I need words

### 8. Losing my mind

Bro just said dyadic and monadic I'm not smart enough for this

HE MADE A DENOTATIVE LANGUAGE THE OPPOSITE OF IMPERATIVE :O

NONE OF THE NEXT 700 PROGRAMMING LANGUAGES DID THIS 💀

### 9. I understand now
THE GOAL OF THIS LANGUAGE IS TO STANDARDIZE HOW WE EXPLAIN WHAT SOMETHING IS

INSTEAD OF HAVING 90000 WAYS TO DO IT, EVERY WAY WOULD BE THE SAME, LIKE FOR EXAMPLE IF WE USE A FUNCTION ONE TIME SOMETIMES WE HARDCODE SAID FUNCTION, BUT WITH THIS LANGUAGE WE HAVE TO DESCRIBE SAID FUNCTION WITH GENERICS

### 10. All my homies hate goto
This paper might've been the start of people hating on goto

This section I think predicts modern control flow in functional languages, hell it might've directly influcend it

### 11. Conclusion
There are three wolves inside of PL development, syntax, what should be considered obvious, and flow control

Thank you for comming to my ted talk

## Did blud predict the next 700 programming languages?
[No 💀.](https://www.youtube.com/watch?v=vcZRDvh3ddE)

