# APL For Astronomy

![APL](apl.svg.png)
<!-- end_slide -->

# APL For Astronomy?

![APL](apl.svg.png)

<!-- end_slide -->

# Array Programming Languages
* Language primitives that operate on vectors
* Fortran, Matlab, Julia, etc
* Can be concise for data manipulation

<!-- end_slide -->
# Python

```python
[1, 2, 3] + [1, 1, 1]
```

<!-- pause -->

```python
[1, 2, 3, 1, 1, 1]
```

![image caption](trash.jpg)
<!-- end_slide -->
# An Array Language

```apl
1 2 3 + 1 1 1
```

<!-- pause -->

```apl
2 3 4
```
![image caption](chad.jpg)
<!-- end_slide -->

# APL
Invented in 1957 by Kenneth Iverson
![Iverson](iverson.jpg)

<!-- end_slide -->

# Notation as a Tool For Thought
![Notation](notation.png)

<!-- end_slide -->

# Notation as a Tool For Thought
* Introduced APL
* Stresses the impact of notation on cognitive process
	* (if you think in Python, you think in scalars)
* Linguistic Relativity for programmers?
* Big hate on mathematical notation - requires too much context for whatever domain it's being used in. 
	* Argues for a unified language that merges the strength of mathematical notion with the universality of general programming languages. 

<!-- end_slide -->

# What does it look like?
<!-- jump_to_middle -->
<!-- alignment: center -->

(~R∊R∘.×R)/R←1↓⍳R
==================
<!-- pause -->
Hint: 
<!-- pause -->
APL is read from right to left
<!-- end_slide -->

# Yes you need a special keyboard
![image caption](characters.png)
<!-- end_slide -->

# Yes you need a special keyboard
![image caption](Ibm.jpg)
<!-- end_slide -->

# Arrays
<!-- alignment: center -->
```
1 2 3 4
```
<!-- end_slide -->

# Arrays
<!-- alignment: center -->
```
⍳4
```
<!-- pause -->
```
1 2 3 4
```
<!-- end_slide -->

# Ranks
<!-- alignment: center -->
```
2 2⍴⍳4
```
<!-- pause -->
```
1 2
3 4
```
<!-- end_slide -->

# Ranks
<!-- alignment: center -->
```
5 5⍴0
```
<!-- pause -->
```
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
```
<!-- end_slide -->

# Arithmetic
<!-- alignment: center -->

```
1 + ⍳3
```
<!-- pause -->

```
2 3 4 5
```
<!-- end_slide -->

# Arithmetic
<!-- alignment: center -->

```
2 * ⍳3
```
<!-- pause -->

```
2 4 8 16
```
<!-- end_slide -->

# Arithmetic
<!-- alignment: center -->

```
2 × ⍳4
```
<!-- pause -->
```
2 4 6 8
```
<!-- end_slide -->

# Equality
<!-- alignment: center -->
```
4=5
```
<!-- pause -->
```
0
```

```
4=4
```
<!-- pause -->
```
1
```

<!-- end_slide -->

# Assignment
<!-- alignment: center -->
```
x←!4
x
```
<!-- pause -->
```
24
```
<!-- end_slide -->

# Black Body Radiation (Wien's Law)
<!-- alignment: center -->
```
sun ← 5772
(2.897×10*-3)÷sun
```
<!-- pause -->
```
5.019057519E¯7
```

About 502 nanometers

<!-- end_slide -->
# Absolute Magnitude
Rigel
```
visual_m ← 0.12
d_ly ← 860
visual_m - 5×(10⍟(d_ly÷3.2616))-1
```
<!-- pause -->
```
¯6.985338764
```
Abslute magnitude of -7
<!-- end_slide -->

# Median of a vector
<!-- alignment: center -->
```
median←{v←⍵[⍋⍵]⋄.5×v[⌈¯1+.5×⍴v]+v[⌊.5×⍴v]}
```
First, the input vector ⍵ is sorted with ⍵[⍋⍵] and the result placed in v. If the dimension ⍴v of v is odd, then both ⌈¯1+.5×⍴v and ⌊.5×⍴v give the index of the middle element. If ⍴v is even, ⌈¯1+.5×⍴v and ⌊.5×⍴v give the indices of the two middle-most elements. In either case, the average of the elements at these indices gives the median.
<!-- pause -->
```
x←10⍴⍳3
```
<!-- pause -->
```
median x
1.5
```
<!-- end_slide -->

# Bonus
Remember that function from the start?
```
R←10
```

```
(~R∊R∘.×R)/R←1↓⍳R
```
<!-- pause -->
```
2 3 5 7
```
<!-- end_slide -->

# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Get the array from 1 to 10
```
⍳R
```
<!-- pause -->
```
1 2 3 4 5 6 7 8 9 10
```
<!-- end_slide -->

# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Drop (↓) the first element of the array
```
1↓⍳R
```
<!-- pause -->
```
2 3 4 5 6 7 8 9 10
```
<!-- end_slide -->
# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Set R to the result of the previous step
```
R←1↓⍳R
R
```
<!-- pause -->
```
2 3 4 5 6 7 8 9 10
```
<!-- end_slide -->

# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
/ is the "replicate n times" (dyadic) operator, so we have to evaluate the left had side. Return to this in a few slides.
```
???/R←1↓⍳R
```
<!-- end_slide -->

# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Generate the outer product of RxR (multiplication table):
Reminder: R <- 2 3 4 5 6 7 8 9 10
```
R∘.×R
```
<!-- pause -->
```
 4  6  8 10 12 14 16 18  20
 6  9 12 15 18 21 24 27  30
 8 12 16 20 24 28 32 36  40
10 15 20 25 30 35 40 45  50
12 18 24 30 36 42 48 54  60
14 21 28 35 42 49 56 63  70
16 24 32 40 48 56 64 72  80
18 27 36 45 54 63 72 81  90
20 30 40 50 60 70 80 90 100
```
<!-- end_slide -->

# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Build a vector the same length as R with a 1 in every place where the number in R is NOT in the multiplication table (like a mask)
```
R∊R∘.×R
```
<!-- pause -->
```
0 0 1 0 1 0 1 1 1
```
<!-- pause -->
```
2 3 4 5 6 7 8 9 10

 4  6  8 10 12 14 16 18  20
 6  9 12 15 18 21 24 27  30
 8 12 16 20 24 28 32 36  40
10 15 20 25 30 35 40 45  50
12 18 24 30 36 42 48 54  60
14 21 28 35 42 49 56 63  70
16 24 32 40 48 56 64 72  80
18 27 36 45 54 63 72 81  90
20 30 40 50 60 70 80 90 100
```
<!-- end_slide -->

# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Logically negate the mask 
```
~R∊R∘.×R
```
<!-- pause -->
```
1 1 0 1 0 1 0 0 0
```
<!-- pause -->
```
Reminder:
R←2 3 4 5 6 7 8 9 10
```
<!-- end_slide -->
# Bonus
```
(~R∊R∘.×R)/R←1↓⍳R
```
Now that we have the mask, we can finally use the Replicate operator. Replicate each item in the right side N times by each member of the left hand array. So, 0 times means that item is removed from the right side:
```
(1 1 0 1 0 1 0 0 0)/R
```
<!-- pause -->
```
2 3 5 7
```
<!-- end_slide -->

# Suggestions for equations to try?

