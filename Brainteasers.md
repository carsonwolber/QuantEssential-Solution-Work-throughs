# Brainteasers
## 18 Sides
### Problem: There is a fair 18-sided die where each side is either a 6 or a 3. The expected value of a roll is 4. How many 6s are on the 18-sided die?

The first thing you should do when solving any problem really, is to ask yourself 1. What is the problem asking for 2. What do we know and 3. How can we use it to make progress towards the desired solution? So let's put this idea into action. 

1. What is the problem asking for? well the unhelpful answer is "How many 6s are on the 18-sided die?". The much more helpful answer is to recognize this is asking for the **ratio** of fours to sixes that will make the expected value for a fair die with 18 sides 4.

2. Since this is my first solve, I'll belabor the point that usually just saying "There is a fair 18-sided die where each side is either a 6 or a 3. The expected value of a roll is 4." isn't all that helpful. However, this is actually a bit of an exception since this information is pretty nicely laid out for us.

3. This part is the one that separates the real problem-solvers from the masses. I personally use this step to get things in math notation as quickly as possible. Because we want an expectation, we can make a random variable $R$ denote a roll of this die. From 2. we have $Ex[R] = 4$. Recognizing this isn't very helpful, let's revert back to 1. and recall it's the **ratio** of fours and sixes that make this equation possible we want, so it'd behoove us to elaborate further on this $Ex[R]$ equation to be more broadly $\frac{\sum side values}{18}$ so we have $Ex[R] = 4 = \frac{\sum side values}{18}$. Now we're getting somewhere!


Let's solve this by first simplifying our current equation: 
$$Ex[R] = 4 = \frac{\sum side values}{18}$$
$$\sum side values = 72$$
This is helpful because it serves as a check that we got it right. That's because as I've been hinting at, the real hint here is to recognize the ratio of 4's and 6's and that we can use any factor of 18 to get an equivalent easier example and extrapolate using that example. So let's consider a fair 3-sided die such that $Ex[R] = 4 = \frac{12}{3}$.  We're guaranteed at least one of each a 6 and 3 on our die (otherwise the expectation couldn't possibly be 4). So have 6+3 = 9 from the beginning and thus need another 3 to get that full 12. And there you have the **2:1** ratio of 3's to 6's that if we extrapolate to 18 sides gives us 12 3's and **6** 6's. We can verify this makes sense by noting 6x6 + 12x3 = 72. 

So our answer is **6** 6's. 


## Multiple Divisors

### Problem: Find the probability that a randomly selected integer from the set of positive divisors of $10^99$ is divisible by $10^80$

1. What is the question asking for? A probability, or for our sake the ratio of positive divisors of $10^99$ divisible by $10^80$ to positive divisors of $10^99$. So to solve this problem, we'll have to reason about divisors for $10^n$ generally.
2. What do we know? This question may not be as applicable in something as rote as this question, but it can still be a useful opportunity to lay out some facts. I first considered the raw cardinality of divisors, which is important to act as our denominator in the ratio. Consider that any $10^n$ can be factored into $(2*5)^n = 2^n * 5^n$. Any divisor of $10^n$ can be written as $2^m * 5^\ell$ for $m,\ell \in [0, n]$ which yields $(n+1)(n+1) = (n+1)^2$ total divisors. So $10^99$ has $100^2$ divisors.  

## Cat Dog Line
### Problem: You're walking down an infinite street, and you notice that six out of every seven cats on a sidewalk are followed by a dog, while one out of every four dogs is followed by a cat. What proportion of animals on the sidewalk are dogs?


1.  What is the problem asking for? It's asking for a proportion. This suggests we need to find a representative arbitrary interval and find the number of dogs over the total animals (dogs + cats)
2.  What do we know? We know that if we just passed a cat, the probablility of seeing a dog next is $\frac{6}{7}$ and that the probability of seeing a dog after we just past one last time is $\frac{3}{4}$. From these we can deduce the probabilies of cat->cat and dog->cat as well to just be 1 - the counterpart. We also know the series is infinite. This is helpful because it allows us to employ that abstract interval idea and know that'll be effective since on an infinite scale the expected lengths will be actually representative rather than being approximations. 
3.  How can we use what we're given to make progress towards the desired solution? This is a pretty visual brute force solution, however we're given a line so we should consider a subset of the line. We can use the given probabilies to create some abstract subset where we perfectly follow the expected number of cats/dogs given the probabilities and tally it up. Again to be clear, this works because on an infinite scale, the answer will converge on the expected value.

Alright, now let's set up this scenario. I approached this with the question "given we just passed a cat, how many dogs will we pass before we see a cat and then another cat?" I chose this idea because seeing a cat and then another cat is clearly the rarest outcome only happening $\frac{1}{7}$ times we see 1 cat. So by considering this idea, we essentially capture an arbitrary microcasm of the whole line. So what does the interval look like? well my idea was, given a cat, 6/7 times it's followed by a dog which will 3/4 times be followed by another dog. So if we just take this literally and go through 6 sets of 1 cat followed by 4 dogs we can derive the expected value. 


With that in mind my brute force method simply consisted of this visual:

… -> cat(1) -> 4 dogs -> cat(2) -> 4 dogs -> … cat(6) -> 4 dogs -> cat(7)-> cat(8) -> … 

Again, the idea is that in expectation, this pattern will go on forever, because every 7th cat will have another cat right after it and every 4th dog is followed by a cat. So we take the probabilities very literally to get this arbitrary expected subset and thanks to the infinite nature of the line conclude the proportion of dogs in the subset this must be equivalent to the proportion in the whole line. So that's the intuition, but what's the proportion? We have 6 sets of 4 dogs so 24 in full and 7 cats (the 7th cat, not the 8th marks the end of the interval since it's the 7th cat we care about because it's followed by the 8th, the 8th itself is nothing special).

24+7 = 31 animals so the proportion of dogs on the line is $\frac{24}{31}$.
