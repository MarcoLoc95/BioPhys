# Uncertainty and errors
If there needs to be one thing you must remember from this lesson, let it be this: every measurement or prediction in physics comes with an associated uncertainty. Always, no exception. That is because measurements provide an *estimate* of the true value, not the true value itself. 

In the context of quantitative measurements, the words **uncertainty** and **error** are sometimes used interchangeably. To be precise, error generally refers to the difference between a measured value and the true or accepted value, while uncertainty is an estimate of the range within which the true value is likely to lie, considering all known errors.

We cannot stress it enough: uncertainty is always present, whether we are reporting a measurement or making a prediction from the theory. Therefore it is important to know how to handle it quantitatively, regardless of where your interest in biophysics will take you.

> **Philosophical digression**
>
>But what about the fundamental constants on Nature, like for example the speed of light in vacuum? Do they come with an uncertainty too? In principle no, but only because they become [axioms](https://en.wikipedia.org/wiki/Axiom) of the physical framework used. For this we must be certain that they are *really* constant. In other words, whenever measured properly, the obtained value must always be within the range of uncertainty. In that case and that one only, it can be considered a fixed value of Nature and reported without error. The idea that, if we use better, more sensitive measuring tools, we would still get the same value, just with a smaller uncertainty.
>
>Not for nothing, the speed of light in vacuum is so constant it is used together with the definition of [second](https://en.wikipedia.org/wiki/Second) to define indirectly what the [meter](https://en.wikipedia.org/wiki/Metre) is. In the next chapter we will talk about units and dimensions, and we will come back at it.
>

### Types of errors
There are countless reasons why we cannot be certain about the values we measure. Consider for instance the measuring of the length of the table: maybe the length changes slightly from side to side due to imperfect manufacturing, or the meter we use cannot reach micrometric precision, or we accidentally measure between two points that are not exactly parallel to the length, or some evil crazy scientist replaced the meter with an inaccurate one, and so on. Some of this errors can be prevented, some other cannot. This does not mean that we cannot be precise in our scientific claims, but only that we acknowledge that what we know is limited to the tools we have to explore Nature. 

Errors are generally classified between these categories:
- **Random errors**: Variations that occur unpredictably from one measurement to another, mostly due to the nature of the process. They cannot be minimized at the source, but they can be reduced by averaging over a large number of observations. An example are the differences in protein concentrations expressed by the same cell line.
- **Systematic errors**: These are consistent, repeatable errors due to flaws in measurement instruments or procedures. Most systematic errors take the form of *biases*. They can and should be minimized at the source by properly calibrating the system. Unlike random errors, systematic errors cannot be reduced by increasing the number of observations. An example is not accounting for the mass of the weighing paper when measuring the weight of a powder.
- **Blunders**: These are careless human errors that happen randomly and result in (completely) off results. Compared to systematic errors, blunders are due to tiredness or negligence and generate biases hard to quantify. They can be minimized with good attention, careful practices and supervision of other colleagues who can point out the obvious mistakes. An example is pipetting $1\,mL$ of trypsin instead of $1\,\mu L$, or recording a $9$ instead of a $6$ onto a lab report.

Some textbooks do not distinguish between systematic errors and blunders; here I want to stress that, while systematic errors can in some cases be corrected in retrospective, blunders should be categorically excluded from analysis.
 
### Instrument resolution
Take a ruler and ask yourself: can I measure micrometers with this?

The answer is no. That is because the spacing between ticks on the ruler is $1\,mm$: finer ticks would be hard if not impossible to see with the naked eye, and due to [parallax](https://en.wikipedia.org/wiki/Parallax) they would literally be useless as different observers would report different measurements.

The instrument resolution (sometimes called *sensitivity*) represents the smallest increment an instrument can reliably measure, its "least count".

If we are measuring the length of a table, even after removing all other sources of errors, we cannot get an estimate of the true value more precise than the resolution of the measuring tool used. The only way to reduce this uncertainty is to use more sensitive tools with better resolution.

### Correctly reporting a measurement
The usual way to report a physical quantity $X$ with its best estimate $x$ and its error $e_x$ is:

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

If at this point you are still a bit confused, I suggest you to practice with some exercises, because correctly reporting measurements and predictions is one of the most fundamental skills in physics.

### Statistics of random errors
When we say "random" we do not imply "unquantifiable". If for example we consider the height distribution of various species of trees, we can still

Wu, Y.; Zhang, X. Object-Based Tree Species Classification Using Airborne Hyperspectral Images and LiDAR Data. Forests 2020, 11, 32. https://doi.org/10.3390/f11010032 

Probability to measure a certain value
Probability density $p(x)$
Mean, variance, standard deviation
Model for $p(x)$: Gaussian distribution with parameters $\mu$ and $\sigma$
Estimates for $\mu$ and $\sigma$ from discrete measurements: mean, corrected sampled standard deviation, root mean squared error
Standard deviation of the mean: Central limit theorem
Standard error of the mean$m$
Relative error

### Which error to choose?
Say the sensitivity of an instrument is $s$. By using this instrument we collect many data points and we calculate the standard deviation $\sigma$. Which value to use as an uncertainty?

The short answer is: the largest value between $s$ and $\sigma$. That's because if the standard deviation is below the sensitivity, the individual variations may just be due to the imprecision of the instrument and not to a natural random variability. However, if the standard deviation is greater than the sensitivity, we know that the individual variations are all well measured with the instrument, despite its limited resolution.

### Those darn outliers
a

# Error propagation
Recap: Taylor expansion
Taylor expansion of the velocity
General formula
Special case of power laws