# General Interview Prep
Here is where I will outline general interview strategies, my favorite questions to ask, and things like that.

## General Interview

##### Outco Article
Some good notes in this Outco Article [The Algorithm of Solving Algorithms](https://medium.com/outco/the-algorithm-of-an-algorithm-28043fe47b51). Includes things like which questions to ask. Breaks up into main categories:
1. Ask More Questions
2. Try more (and bigger) examples
3. Become the Algorithm (really this is about taking a step back)
4. Distill the Problem to its Essence
  * __Interesting Point:__ Write down *what* your solution is going to do in one sentence (harder problems can get 2-3). Beneath it list the key points and some of the implementation notes. Only then can you begin actually implementing.
  * A correlary: Express parts of the problem statement in one sentence. Example: palindromes have at most one letter that occurs an odd number of times.
5. Pseudocoding
  * By spending 5 minutes here you build a source of truth that may save your interview
6. Coding
  * If you do the above correctly then this step should be trivial
### Solving a Problem Tips

#### DOs

#### DONTs
* If you recognize the problem, don't just try and recall the solution. Try to recall some of the key points that you remember and right them down, but don't just write down the solution from memory. Instead, focus on solving it like normal but use the points you remember for guidance if you get stuck

**TODO**: Copy in [this](https://www.docdroid.net/M2JiyIt/two-minute-drill.pdf) 2-minute drill

## Problems and Approaches

### Dynamic Programming

#### Memoization
TODO
##### Outco Article on Memoization
Another Medium [Article](https://medium.com/outco/how-to-implement-memoization-in-3-simple-steps-83758b2439a) about Memoization

* All Memoization is doing is reducing the amount of work that your helper method needs to do!
* For Memo to work, there should be identical work between recursive calls. Otherwise, we won't be able to store computations and achieve a speedup.

###### Steps for Recursive Memo
1. Create your memo table (hashmap, array, etc.) in the outer function's scope.
2. Add a check for the base case, or if needed data exists in memo table, to your recursive function.
3. Store the return value of each recursive call in the proper location of memo table before actually returning it.

#### Tabulation
TODO

#### Sliding Window
Interesting [article](https://medium.com/outco/how-to-solve-sliding-window-problems-28d67601a66) that covers the ideas below.

###### Sliding Window Tips
* Thinking about the constraints on the problem can lead to a *key insight* which helps you determine which window to use.

###### Spotting a Sliding Window Problem
* Problem involves an ordered data structure like an array, string, or list.
* You are looking for some subarray in the DS; like a longest substring, or shortest subarray.
* Biggest Giveaway: What you are looking for is an optimal substructure that satisfies some given condition exactly.

###### Types of Windows
A window represents a current section of the DS that you are looking at, usually denoted with pointers (one for the start and one for the end) and information relating to the constraints (maybe the current sum of this window).
**Fast + Slow**
* One pointer grows the window quickly via its condition (in MinWindow Substring, grow until you contain all of the characters).
* Other pointer shrinks the window. (i.e. shrink the window until you no longer have the valid characters)
**Fast + Catchup**
* Similar to Fast+Slow, except the back pointer simply jumps to the front pointers location under a certain condition.
  * In MaxSum, the back pointer would teleport when your current sum goes negative.
**Fast + Lagging**
* The back pointer is just a couple of indices behind the front pointer.
  * In House Robber, we know that the maximum distance between robs is 2 (since 3 would allow us to rob the middle). This creates a bound on our back pointer.
* The back pointer usually keeps track of a previous choice.
  * In the House Robber problem, your back pointer might keep track of the last house you robbed and its amount.
**Front + Back**
* Different than the above, since now pointers are converging towards the middle.
  * Used in problems such as Rainwater.

