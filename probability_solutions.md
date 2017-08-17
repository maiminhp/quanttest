## Probability Solutions
Minh Pham

minh.pham@columbia.edu

October 13, 2016

### Solutions


#### Question 1: We randomly select 4 numbers from the set of the first 16 prime numbers, without replacement. What is the probability their sum is even? Why? 

#### Solution: 

Their sum is even when none of them is $2$ (the first prime number.)

In order to calculate the desired probability, we take all the ways in which 4 numbers can be picked from 16 numbers as the denominator. As the numerator, we compute how many ways to not select $2$ out of these 16 prime numbers. It looks something like this:
$$
{{15}\choose{4}} / {{16}\choose{4}} = \frac{3}{4}
$$

#### Question 2: You have been chosen to play a game involving a 8-sided die. You get to roll the die once, see the result, and then may choose to either stop or roll again. Your payoff is the sum of your rolls, unless this sum is greater than 8, in which case you "bust" and get nothing. What is your strategy for this game? That is, for each possible outcome of the first roll will you choose stop or to roll again?

#### Solution:

If you roll a 1, your $P(losing) = \frac{1}{8}$ if you roll again. In other words, you can only lose if you roll an $8$ in the next roll which gives you a 1 in 8 chance of losing. Similarly, you can construct the below table.

Let $X_1$ denote the result of the first roll and $X_2$ denote the result of the second roll.

| $X_1$               |  $P(losing)$  | 
|--------------------:|-----------------------------:|
| 1 | $P(X_2 = 8) = \frac{1}{8}$    |
| 2 | $P(X_2 = 7,8) = \frac{2}{8}$  |
| 3 | $P(X_2 = 6,7,8) = \frac{3}{8}$  |
| 4 | $P(X_2 = 5,6,7,8) = \frac{4}{8}$  |
| 5 | $P(X_2 = 4,5,6,7,8) = \frac{5}{8}$  |
| 6 | $P(X_2 = 3,4,5,6,7,8) = \frac{6}{8}$  |
| 7 | $P(X_2 = 2,3,4,5,6,7,8) = \frac{7}{8}$  |
| 8 | $P(X_2 = 1,2,3,4,5,6,7,8) = \frac{8}{8} = 1$  |

If you roll anything larger than $4$, you have more than $50\%$ of going 'bust' if you decide to roll again. 

**Strategy**: 
- If you roll anything $\leqslant 4$ on the first roll, roll again. 
- If you roll anything $>4$ on the first roll, don't roll again.

#### Question 3: A bag has three coins in it which are visually indistinguishable, but when flipped, one coin has a 20% chance of coming up heads, another as a 20% chance of coming up heads, and the last has 60% chance of coming up heads. I randomly draw a coin from the bag and flip it, and the result comes up heads. What is the probability that if I reflip this coin, it will come up heads again? Why?

#### Solution: 

Let $C_1, C_2, C_3$ denote the three coins respectively, and $F_1, F_2$ to denote the result of the first flip and second flip respectively. $X$ is the coin that we've randomly drawn.

What we're trying to compute is really the following conditional probability:

$$
P(F_2 = H | F_1 = H) = \frac{P(F_1 = H, F_2 = H)}{P(F_1 = H)} (1)
$$

Now, let's deal with the denominator first. What is the probability of getting heads on the first flip?

$$
P(F_1 = H) = P(F_1 = H \cap X = C_1) + P(F_1 = H \cap X = C_2) + P(F_1 = H \cap X = C_3)
$$
$$
= P(F_1 = H \mid X = C_1)P(X = C_1) + P(F_1 = H \mid X = C_2)P(X = C_2) + P(F_1 = H \mid X = C_3)P(X = C_3)
$$
$$
= 0.2 \times \frac{1}{3} + 0.2 \times \frac{1}{3} + 0.6 \times \frac{1}{3}
$$

Now, let's compute the numerator.
$$
P(F_1 = H, F_2 = H) = P(F_2 = H \cap F_1 = H \cap X = C_1)
$$
$$
+ P(F_2 = H \cap F_1 = H \cap X = C_2)
$$
$$
+ P(F_2 = H \cap F_1 = H \cap X = C_3)
$$
$$
= P(F_2 = H \mid F_1 = H)P(F_1 = H \mid X = C_1)P(X = C_1)
$$
$$
+ P(F_2 = H \mid F_1 = H)P(F_1 = H \mid X = C_2)P(X = C_2)
$$
$$
+ P(F_2 = H \mid F_1 = H)P(F_1 = H \mid X = C_3)P(X = C_3)
$$
$$
= 2\times 0.2^2\times \frac{1}{3} + 0.6^2\times \frac{1}{3}
$$

$$
\Rightarrow (1) = \frac{2\times 0.2^2 + 0.6^2}{2\times 0.2 + 0.6}
$$
$$
\Rightarrow (1) = 0.44 = 44\%
$$


#### Question 4: We have two urns. You can't tell them apart from the outside, but one has four $1 chips and six $10 chips, and the other has three $1 chips and seven $10 chips. You randomly draw a chip from one of the urns and it happens to be a $1 chip. Without replacing this draw, I offer you a chance to draw and keep a chip from either urn. Should you draw from the same urn or the opposite urn, and what is the expected value of the chip you draw? Why?

#### Solution: 

- Urn 1: $4\times \$1$, $6\times \$10$
- Urn 2: $3\times \$1$, $7\times \$10$

Let $X$ denote the urn that you drew the $\$1$ chip from. Because there's a 50-50 chance of picking either urn. Therefore, we have the odds of picking _urn 1_ to picking _urn 2_ is 4 to 3 or to put it another way:

$$
\frac{P(X=1)}{P(X=2)} = \frac{4}{3}
$$

Now in order to decide which urn to pick for our next draw, it's best that we compute the expected value drawn from the selected urn ($X$) and the other urn ($Y$) after our observation.

$$
\mathbf{E}(X) = \mathbf{E}(X\mid X = 1)P(X=1) + \mathbf{E}(X\mid X=2)P(X=2)
$$
$$
= \frac{3\times \$1 + 6\times \$10}{9}\times \frac{4}{7} + \frac{2\times \$1 + 7\times \$10}{9}\times\frac{3}{7}
$$
$$
\approx \$7.43
$$

and the expected value of the other urn:

$$
\mathbf{E}(Y) = \mathbf{E}(Y\mid X = 1)P(X=1) + \mathbf{Y}(Y\mid X=2)P(X=2)
$$
$$
= \frac{3\times \$1 + 7\times \$10}{10}\times \frac{4}{7} + \frac{4\times \$1 + 6\times \$10}{10}\times\frac{3}{7}
$$
$$
\approx \$6.91
$$

_Conclusion:_ If our computation was correct, I'd go ahead and pick a chip from the current urn. And the expected value of that chip is $\approx\$7.43$
