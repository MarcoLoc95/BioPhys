# Units and dimensions

7 base quantities, with SI units and dimensions
Derived units

### Orders of magnitude

### SI notation
SI notation: prefixes, error notation with significant digits

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

%%%%%%%%%%%%%%%%%%%%%%EXAMPLE WITH Y with units and order of magnitude

If at this point you are still a bit confused, I suggest you to practice with some exercises, because correctly reporting measurements and predictions is one of the most fundamental skills in physics.


### Dimensional analysis: calculation rules for units

> **Philosophical digression**
>
>My friends studying physics keep japping about the speed of light in vacuum being equal to 1. What is this nonsense? Did they completely lose their minds?
>
>The answer is: maybe they did lose their minds (and it's not up to us to judge), but what they state is not false. The reason why they are right is a bit conceptually complicated, but the idea is that, once we establish that a physical quantity is an actual constant, completely independent from any circumstance, we can set that constant to **any** value. Think of this as choosing a conversion factor that makes the math easier. You’re not changing any physical reality, you’re just redefining how you measure things. Of course, all the derived quantities will have a different (but consistent) numerical values. 
>
>Take as an example the speed of light in vacuum $c$. If its canonical value is $c=299792458\,m/s$ it's only because we defined what a meter and what a second are. And this, maybe to the surprise of the reader, are fundamentally arbitrary.
> Say we decide to redefine it to $c=1\,m/s$. The definition of either space or time must change to keep this choice consistent. 
>
> Say we keep the same definition of time because we are still satisfied with it. What is a meter? If we know that in one second light travels $299792458\,m$, then we can say that $1/299792458$ of the distance travelled by light in one second is exactly one meter.
>
>$$
> 1\,m = \frac{c\cdot 1\,s}{299792458} 
>$$
>
>Correct? Well, let's calculate this formula explicity using $c=1$:
>
>$$
> 1\,m = \frac{1\cdot 1\,s}{299792458} =frac{1}{299792458}\,s
>$$
>
>Wait, what?!? The dimensions of length are now the same as those of time? Are time and space the same? Well, according to Einstein and every physicist working with relativity, yes. In relativity, space and time are intertwined into a single framework called spacetime, and the equations become much clearer when $c$ is set to 1. Think for example of the famous equation that relates the energy and the mass, $E=mc^2$: under this new convention, $E=m$. Indeed, mass is essentially "frozen energy" that can be released under certain conditions. In contexts like nuclear physics, this equivalence explain how stars shine and how nuclear reactors work.
>
>It may sound overcomplicated and unnecessary, and for biophysics it is. You may now take a breath of relief: we won't need to change the definitions of fundamental dimensions. But I think it's good, sometimes, to challenge your understanding of reality and Nature, hence this long digression.
>