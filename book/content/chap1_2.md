# Uncertainty and errors
If there needs to be one thing you must remember from this lesson, let it be this: every measurement or prediction in physics comes with an associated uncertainty. Always, no exception.

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

Errors are generally classified between these three categories:
- **Random errors**: Variations that occur unpredictably from one measurement to another, mostly due to the nature of the process. They cannot be minimized at the source, but they can be quantified and accounted for. An example are the differences in protein concentrations expressed by the same cell line.
- **Systematic errors**: These are consistent, repeatable errors due to flaws in measurement instruments or procedures. Most systematic errors take the form of *biases*. They can and should be minimized at the source by properly calibrating the system. An example is not accounting for the mass of the weighing paper when measuring the weight of a powder.
- **Blunders**: These are careless human errors that happen randomly and result in completely off results. Compared to systematic errors, blunders generate bigger biases and are due to tiredness or negligence. They can be minimized with good attention, careful practices and supervision of other colleagues who can point out the obvious mistakes. An example is pipetting $1\,mL$ of trypsin instead of $1\,\mu L$, or recording a $9$ instead of a $6$ onto a lab report.

Some textbooks do not distinguish between systematic errors and blunders; here I want to stress that, while systematic errors can in some cases be corrected in retrospective, blunders should categorically be excluded from analysis.

### Correctly reporting a measurement
In fact, measurements without their range of validity are meaningless.
How to report a measurement with its error and significant digits. Rounding rules.
+ relative error


### Distribution of statistical errors
Probability to measure a certain value
Probability density $p(x)$
Mean, variance, standard deviation
Model for $p(x)$: Gaussian distribution with parameters $\mu$ and $\sigma$
Estimates for $\mu$ and $\sigma$ from discrete measurements: mean, corrected sampled standard deviation, root mean squared error
Standard deviation of the mean: Central limit theorem
Standard error of the mean$m$

### Error propagation
Recap: Taylor expansion
Taylor expansion of the velocity
General formula
Special case of power laws