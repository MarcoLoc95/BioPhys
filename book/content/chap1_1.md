# Quantitative descriptions

Quite some years ago, on a lovely afternoon, my mom and her sister were chatting in the living room. Then, as my aunt was nostalgically reminiscing about their mother's cooking skills, a heated argument suddenly sparked. Disturbed by the sudden chaos in the house I decided to go talk to them to see what the quarrel was about. It turned out that the disagreement was about the exact quantity of flour needed to bake my grandma's world renowned apple pie. My mom claimed that any deviation from the canonical $200\,g$ of flour would completely ruin the pie, while my aunt insisted that later adjustments to the recipe optimized the quantity to $230\,g$. Unfortunately, my grandma never wrote down her recipes, maybe in a bitter attempt not to share her culinary secrects with her envious cousins. To settle the argument, I cleverly proposed a bake-off, where I would be the judge, and they both accepted the challenge. After sampling two delicious pies in a repeated blind experiment, I could not tell the difference between the two, and the family had to reach a compromise that both versions of the apple pie were acceptable and valid.

Why did the pies turned out to be undistinguishable? The main reason is because the quantity of flour was not reported scientifically. Not only because it was not properly documented, but most importantly because the acceptable values were in a certain range. Imagine if one single gram of flour would dramatically change the taste of a dessert: restaurants would look more like high precision laboratories, and cooking at home would be a nightmare. Assuming that in my family's quirrel the truth was in the middle, and both variations would still be acceptable, the amount of flour should have been reported as following:

$$
 m_{\text{flour}}=(215\pm 15) g
$$

This notation unambiguously tells us that any value between $200$ and $230$ would result in the same outcome. This is what we call a **quantitative description**. It is easily testable: one could, for example, bake ten pies with varying flour amounts inside and outside this range to validate it. Reproducibility and predictability are the two main advantages of quantitative descriptions.

Science is built of quantitative descriptions and could not live without them.  Thanks to quantitative descriptions we can aim at describing reality in an objective, undisputable way. The goal, in other words, is to get as close as possible to the *true value* of physical quantities.

Now the question is: can we measure the true value of a quantity?

### Accuracy, precision and the true value

One of the most fundamental concepts in physics is the difference between accuracy and precision. To understand it, look at the following illustration:

```{figure} ../figures/chap1_accprec.png
---
width: 80%
name: 1_accprec
align: center
---
Accuracy and precision are not the same thing (adapted from Jono Hey, [Sketchplanations](https://sketchplanations.com/accuracy-and-precision) CC BY-NC 4.0)
```

Accuracy is how close a set of measurements is to the true value. Precision is how close the measurements are to each other. The difference is far from being just semantical: if we use the most sensitive kitchen scale but forget to tare it, the measurements will be precise (small deviation) but not accurate (far from the true value). 

Now look at the following scatter plot:
```{figure} ../figures/chap1_accprec1.png
---
width: 80%
name: 1_accprec1
align: center
---
```
Are our measurements precise? Are they accurate?

The fact is, without prior knowledge regarding the true value, it's impossible to say. But let's now assume that the theory predicts the true value with a certain range of confidence (represented with the bullseye):

```{figure} ../figures/chap1_accprec2.png
---
width: 80%
name: 1_accprec2
align: center
---
```

Now we can say that the measurements were not accurate but had a reasonable precision. With this new information we can either argue that the theory is wrong, or that there is some kind of error in the measurements. This is still a ballpark consideration, and definitely not quantitative yet. 

In the next section we will define uncertainty, what causes it, how to measure it and how to use it to make quantitative statements.