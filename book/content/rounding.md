### Correctly reporting a measurement
We already mentioned that the way to report a physical quantity $X$ with its best estimate $x$ and its error $e_x$ is:

$$
X = x \pm e_x
$$

Imagine you have measured a biophysical property and you estimated its value to be $x=3.29784625$. You also estimate the uncertainty on this measure to be $e_x=0.03527$. How do we report the result correctly?

First of all, we have to look at the error. How do we know its value is not $0.03526$ or $0.03528$? How sure are we on that last digit? Logically we would need to introduce the *error on the error*, but then how well do we know it? Continue like this and you'll end up defining infinite errors iteratively. Now, this approach is not useful to anyone. For this reason we need to slightly approximate the error, and round it to its most significant digits only. The terms significant digits and significant figures can be used, in this context, equivalently.

There are precise **rounding rules** that are worth memorizing. The first zeros are important because they tell us the order of magnitude of the error. If there are no zeros on the left side of the number, then we simply don't need to consider them. Then we look at the first non-zero digit and the one after it:
- If the first digit is a 1 and the second is not 0, we keep both digits and discard all the other afterwards;
- If the first digit is a 1 and the second is 0, we keep only the first digit;
- If the first digit is not a 1 and the second is between 0 and 4 (included), then we **truncate** everything after the first digit;
- If the first digit is not a 1 and the second is between 5 and 9 (included), then we **round up**, meaning we add 1 to the first digit and truncate all the following digits.

```{figure} ../figures/chap1_rounding.png
---
width: 80%
name: 1_rounding
align: center
---
```

So, in our example, the first non-zero digit is 3, followed by a 5. We round up the 5, so the 3 becomes a 4, and we will finally have $e_x=0.04$.

Now we look at the value $x$. If we cannot know the error better than a certain amount of significant digits, we certainly cannot know the value to that precision either. So we count how many digits <ins>the error</ins> has after the dot, and round up or down the value $x$ to have the same amount of digits.

The rounding rules there still hold:
- If the first digit after the last significant digit is between 0 and 4 (included), then we **truncate** everything after the first digit;
- If the first digit after the last significant digit is between 5 and 9 (included), then we **round up**, meaning we add 1 to the first digit and truncate all the following digits.

In the example, $x=\mathbf{3.29}784625$ is marked in bold to have the same amount of digits as the error. Since the first non-significant digit is a 7, we add one to the last significant digit. But because 9+1 becomes 10, the value to report will be $x=3.30$. The last zero is still significant, so we need to report it.

All in all, the correct way to report this quantity is:

$$
 X = 3.30\pm 0.04
$$

Much better, isn't it?