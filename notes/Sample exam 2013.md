---
tags: [FIT2014]
title: Sample exam 2013
created: '2020-11-22T01:47:01.737Z'
modified: '2020-11-22T22:25:15.073Z'
---

# Sample exam 2013
## Question 1
(C or NotH or NotS) AND (NotC or H or NotS) AND (notC or notH or S)

4/0 Marks
## Question 2
### A
A X; UTM(x) => Computer(X)

2/2 Marks
### B
A myPhone; UTM(myPhone) => Computer(myPhone)

2/2 Marks
## Question 3
### A
E, aba, baa,abaaba, ababaa, baabaa, baaabaa

2/2 Marks
### B

2/2 Marks
## Question 4
Prove every cofinite language is regular.
cofinite if it contains all strings over that {a,b} except for some finite number of strings.

First observe that every regular language is any language that can be represented by a FA.
Next notice that the language that contains every possible string of {a,b} is also regular.
Create a FA that only accepts that lanaguages that should not be accepted within the cofinite language, then reverse the accept states to get an FA that accepts the compliment of that language. This is now an FA that accepts cofinite languages.
Therefore all cofinite languages are regular languages.


3/3  Marks
### Question 5

7/7  Marks
### Question 6
Use regular expression to express the language that the anaylisers accepts
Then convert to NFA to FA and run the FA on the input string. If accepts than the lexical anayliser can accept else rejects and the lexical anayliser rejects



3/1.5 Marks

### Question 7
{ a^m b^n: m <  n} use pumping lemma to prove this is not regular.

Language is regular thereforet there is an FA that describes it.
let N be the number of states in the FA
Proof by contradiction? Pumping lemma
By the pumping lemma 
w = xy^iz
for all i > 0 w is accepted
|xy|<= N
|y| > 0

let w = a^Nb^N+1; N is number of states in the FA
Cases
y contains onlys a's
if y contains only a's then i=2 will create xyyz, which will create more or equal the amount of a's then b's as the lowest number of a's that y can have is 1 and increasing by 1 would make a's and b's have equal number breaking m<n

y contains only b's
if y contains only b's then making i=0, makes xz, which reduces the number of b's by at least 1 which would make m=n breaking m<n

y contains both a's and b's
if y contains a's and b's then increaing i would create and loop of a's and b's therefore if i=2 xyyz, and y has a's and b's then it would create an a in between b's or vice versa which does not exist in a^mb^n

Therefore by the pumping lemma the language a^mb^n is not regular.

6/6 Marks


## Question 8
S-> aaSb
S-> empty

2/0 Marks
## Question 9

Proof by induction
Base case the string m=1 and n=1 is accepted which creates ab, empty string is also another base case that is trivially accepted.
1. S->aS
2. S-> Sb
3. s-> Empty

1. aS
2. aSb
3. ab

True for base case
Assume that the string when m = k and n = k is accepted. where k >= 0 
Prove that m=k+1 n = k is accepted and that m = k and n = k+1 is accepted.

Since m=k and n=k is accepted this means the string of m a's and n b's is accepted.
When creating the string m=k and n=k that means that on the last step of creation the S was turned into the empty string. which means the second last step was some number of a's followed by S then followed by some number of b's.
Instead of chanhing S to empty change S to aS to increase to m=k+1 or change S to Sb to make m = k+1 and then Make S empty.

Thus the statement that this context free grammar can create a^mb^n is True proved by proof by induction.

6/4 Marks

## Question 10
Derivaiton
aqrqa
S → aBa (1)
B → BB (2)
B → Q (3)
B → R (4)
Q → q (5)
R → r (6)

Rule 1 aBa
Rule 2 aBBa
Rule 2 aBBBa
Rule 3 aQBBa
Rule 5 aqBBa
Rule 4 aqRBa
Rule 6 aqrBa
Rule 3 aqrQa
Rule 5 aqrqa

2Marks

Parse Tree

## Question 11


## Question 12
That each CFG can be changed to a Pushdown automata

## Question 13

6/6 Marks

## Question 14
Church Turing Thesis?

Why is the thesis accepted

## Question 15
Unde
Deci
Deci
Undeci

Marks 4/4
## Quesiton 16
a: Context free True 
b: Context free False
c: P True
d: NP True
e: P True
f: NP False
g: RE True
h: RE False
i: Decidable False
j: Regular False


10/4 marks

## Question 17
Assume we have a decider R that given input M and x it will accept or reject.

If R exists than use R to create S that solves the halting problem thereby creating a contradiction

Construct S as follows:
run R on M and x if R accepts then S accepts
                 if R rejects then S rejects (R is a decider so will never loop for ever)
Since S will accept or reject the input M and x then S will always HALT given the input M and x thus this contradicts the HALTing problem be undecidable thus R must not exist and the problem is therefore undecidable.

Marks 7/5
## Question 18
It is made under the assumption that M will accept and output this is not decidable thus the enumerator cannot be created in this way.
Marks 2/2

Rather than using acceptance just print the words sequentially.
0/3
## Question 19
Since U can simulate any turing machine in t^4 steps and the big O for the turing machine M is O(n^3) then U would simulate the turing machine M in O((n^3)^4)) which means the big O upper bound is O(n^12)
4/4 marks

## Quesiton 20
Regular langauge are all languages that can be accepted using a FA. Since an FA has a transistion and step to each state then the number of writes is equal to the number of steps taken. This means that regular languages can be expressed in terms of the length of the language meaning the complexity of regular lanagueges is n which is within the polynomial time class of languages meaning that regular langauges are within P

4/3 Marks

## Question 21
it is increase by a constant factor.

2/2 Marks

## Question 22
Prove the language is in NP, thus prove that the language can be verified given a certicate in polyomial time
Create a polynomial time verifier for the problem

Certificate = a NO MONOCHROMATIC TRIANGLE
Input = A graph

For each edge assign black or white, changing each time. 
For each triangle check if the condition is untrue (i.e the edges of the triangle are all the same colour)
If they are change the edge colour.

This algorithm is run in polynomial time as each each is checked at most twice
Therefore it is in NP
4/0 Marks


### B
0/6 Marks

### C
7/0 Marks


### D 
0/2 Marks

### E
to prove that NO MONOCHROMATIC TRIANGLE  is NP -complete you must map NP-Complete proble to NO MONOCHROMATIC TRIANGLE which is done in part c as SAT is NP-Complete
2/2 Marks



