---
layout: post
title: Simpson's Paradox 
katex: True
hidden: 1 
---

In a (fictional) observational study, living in a sunny area improved the
happiness of people over 60. The same thing was true for people under 60. But
when considering all ages, living in sunny regions reduced happiness. Enter,
Simpson's paradox!

At first blush this sounds unbelievable, paradoxical even. How can inhabiting a
sunny location improve happiness in both age groups separately but reduce
happiness in the full population? But the math works out, as we’ll see. This
phenomenon has a name: Simpson’s Paradox. Like all so-called "paradoxes" in
science, that of Simpson is actually quite explainable. Clearly both findings
can't be true.  Understanding Simpson's paradox will let us figure out which of
the two contradicting interpretations in studies like the one above is correct. 

Let's start with the facts. The table below shows results from a fictional
observational study on how inhabiting a sunny or cloudy area influences
happiness.

<div class="figure">
<table>
      <tr>
          <td rowspan=2></td>
          <td colspan=3>Sunny</td>
          <td colspan=3>Cloudy</td>
      </tr>
      <tr>
          <td>Happy</td>
          <td>Unhappy</td>
          <td>&percnt; Happy</td>
          <td>Happy</td>
          <td>Unhappy</td>
          <td>&percnt; Happy</td>
      </tr>
      <tr>
          <td>Age under 60</td>
          <td>3</td>
          <td>1</td>
          <td><strong>75&percnt;</strong></td>
          <td>8</td>
          <td>4</td>
          <td>66&percnt;</td>
      </tr>
      <tr>
          <td>Age over 60</td>
          <td>4</td>
          <td>6</td>
          <td><strong>40&percnt;</strong></td>
          <td>1</td>
          <td>3</td>
          <td>25&percnt;</td>
      </tr>
      <tr>
          <td>Overall</td>
          <td>7</td>
          <td>7</td>
          <td>50&percnt;</td>
          <td>9</td>
          <td>7</td>
          <td><strong>56&percnt;</strong></td>
      </tr>
</table>
<div class="caption" markdown="span">
The results from an observational study on the influence of living in a sunny
location on happiness. The results are separated by age group with those under
60 in the first row, those over 60 in the second, and the combined population
in the third. When separated by age group, the inhabitants of sunny places are
happier, but the full population is happier when living in a cloudy place.
</div>
</div>

For the younger age group, $75\%$ of those living in a sunny location are happy
compared to only $66\%$ of those living in a cloudy region. Similarly, for the
older age group $40\%$ of the sunny residents are happy compared to just $25\%$
of cloudy residents. Living in a sunny region must improve happiness,
regardless of age. If we combine the two age groups, the story flips. In the
sunny region $50\%$ are happy, but in the cloudy region $56\%$ are happy.
Living in a cloudy location must improves happiness, regardless of age.

We have two contradicting interpretations. Which one is right? Does sunniness
make people happy or sad? Certainly it can't be both.

Before resolving this conundrum, let's get familiar with the mechanics of
Simpson's paradox. First, the math itself is sound. At its most basic,
Simpson's paradox can be explained by a simple yet counterintuitive observation
on fractions, sometimes called Simpson's reversal:

\\[ \textrm{Even if both} \; \frac{a}{b} > \frac{u}{v} \; \textrm{and}
\; \frac{c}{d}\gt\frac{x}{y}, \; \textrm{it's possible that} \;
\frac{a+c}{b+d}\lt\frac{u + x}{v + y}.\\]

Go ahead and take a moment to convince yourself this is possible. Here are a
few numbers to try: $a = 4, b = 20, u = 1, v = 6$ and $c = 5, d =
6, x = 16, y = 20$.

Perhaps a more intuitive way to expose Simpson's paradox is with continuous
variables on a graph. The same results from the table above are graphed below.
The only difference is that each observation can take on a range of values for
sunniness and happiness. Overall the proportions falling into each category are
the same.

<div class="figure" style="margin-top:20px;margin-bottom:20px">
<img src="{{ site.base_url }}/images/simpsons-paradox/age_groups.svg" style="width:300px"/>
<div class="caption" markdown="span">
A graph of the happiness of an individual against the sunniness where they
live. The population is split into two age groups. The four quandrants
partition the data to give the same counts as the table above.
</div>
</div>

In the figure above, the four quadrants represent the four possibilities
(unhappy or happy, and cloudy or sunny). The blue dots correspond to the
younger age group and the red dots to the older age group. If we plot the two
groups on separate graphs the trend of increasing happiness with increasing
sunniness is clear, as shown in below.

<div class="figure" style="margin-top:20px;margin-bottom:20px">
<img src="{{ site.base_url }}/images/simpsons-paradox/separate_groups.svg" style="width:600px"/>
<div class="caption" markdown="span">
The same graph as above but separated by age group. The younger population is
on the left ond the older population is on the right. Each age group shows a
clear upward trend of happiness with sunniness. 
</div>
</div>

However, we can also emphasize the aggregation over groups by removing the
colors. If we do this, the trend of decreasing happiness with increasing
sunniness emerges, as shown below. In fact, it's hard to believe
these two graphs are the exact same points&mdash;but they are.

<div class="figure" style="margin-top:20px;margin-bottom:20px">
<img src="{{ site.base_url }}/images/simpsons-paradox/no_groups.svg" style="width:300px"/>
<div class="caption" markdown="span">
The same graph as above for the full population but without any age
distinction. The population as a whole shows a clear downward trend of
happiness with sunniness. 
</div>
</div>

Ok now you believe the results are real. But this doesn't help us answer the
question of what is the right interpretation. Does sunniness increase or
decrease happiness? To answer that, we need to make some assumptions about
causality.

The key decision is whether or not to aggregate the data before drawing a
conclusion. To make that decision, we need to have a view how the variables
influence one another. 

Let's assume first of all the both age and sunniness effect happiness.
Unfortunately for the older group they are less likely to be happy in general
(remember this is fictional!). Let's also assume that age influences sunniness.
Perhaps the older group is more likely to be in Florida (maybe that's why they
are less happy in general). These relationships are summarized in the figure on
the left below, the arrows indicate the direction of influence.

<div class="figure" style="margin-top:20px;margin-bottom:20px">
<img src="{{ site.base_url }}/images/simpsons-paradox/models.svg" style="width:500px"/>
<div class="caption" markdown="span">
<strong>Left:</strong> A possible model for the relationship of the three
variables: age, sunniness, and happiness. In this model we assume that age
effects both sunniness and happiness, and sunniness only influences happiness.
<strong>Right:</strong> A different model replacing age with exercise. In this
case we assume sunniness influences happiness and exercise, and exercise
influences happiness.
</div>
</div>

Overall, the older group is less likely to be happy and more likely to live in
a sunny location. When we aggregate the data over age, this shows up as a
negative correlatation of happiness with sunniness. But this interpretation is
simply an artifact of the influence of age on choice of habitat. In the
language of causality, age is a confounding variable and must be controlled
for. Here, the right approach is to group by age then interpret the findings.

Consider a different study. Instead of age, we measure the amount of exercise.
All the numbers are exactly the same. In this case, the model probably looks
more like the right version figure above. Sunniness effects happiness directly
as does exercise. But sunniness also effects exercise, a reasonable assumption
given that people often prefer outdoor recreation. So sunniness indirectly
effects happiness on exercise. If our goal is to estimate the effect of
sunniness on happiness, grouping by high exercise (the former older group)
versus low exercise (the former younger group) doesn't make sense. In this case
we wouldn't see the difference in happiness due to the indirect influence of
sunniness through the amount of exercise. Here, the right approach is to
aggregate the population then interpret the findings.

These cases are not meant to be comprehensive, just to demonstrate that the
correct interpretation of the study in the precense of Simpson's paradox
depends on the causal relationship between variables. To choose correctly we
often need to make assumptions. If we don't know whether or not age influences
choice of habitat, then we need to be extra cautious when interpreting the
effect of sunniness on happiness.

The inspiration for this post was drawn from Chapter 6 of Judea Pearl’s
*The Book of Why*, which I recommend for a more thorough explanation of
Simpson's paradox.[^pearl] The Wikipedia page also has some classic historic
examples of Simpson’s paradox found in real observational
studies.[^wikisimpson]

### References

[^pearl]:
    Judea Pearl and Dana Mackenzie. *The Book of Why: The New Science of Cause and Effect*, 2018.
    [(link)](http://bayes.cs.ucla.edu/WHY/)

[^wikisimpson]:
    Simpson's Paradox, Wikipedia [(link)](https://en.wikipedia.org/wiki/Simpson%27s_paradox)
