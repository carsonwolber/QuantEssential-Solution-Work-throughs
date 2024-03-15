# QuantEssential-Solution-Work-throughs
This is my attempt to document and meticulously explain my solutions to the free blind 75 questions on QuantEssentials.io. 

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
This is helpful because it basically serves as a check that we got it right. That's because as I've been hinting at, the real hint here is to recognize the ratio of 4's and 6's and that we can use any factor of 18 to get an equivalent easier example and extrapolate using that example. So let's consider a fair 3-sided die such that $Ex[R] = 4 = \frac{12}{3}$.  We're guaranteed at least one of each a 6 and 3 on our die (otherwise the expectation couldn't possibly be 4). So have 6+3 = 9 from the beginning and thus need another 3 to get that full 12. And there you have the **2:1** ratio of 3's to 6's that if we extrapolate to 18 sides gives us 12 3's and **6** 6's. We can verify this makes sense by noting 6x6 + 12x3 = 72. 

So our answer is **6** 6's. 
