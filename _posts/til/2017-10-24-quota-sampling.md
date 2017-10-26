---

layout: post
title: "TIL about Quota sampling and it's relationship with selection bias."
categories: til

---

TIL about the *Quota Sampling*. The idea is very simple. You want to sample a population for a survey or an experiment. Hence, it's important that your sample accurately represents the sub populations within the population. If gender ratio is 1 female for every 1.2 male in the whole population, you should make sure that your sample follows the same ratio. But for your survey, it may also be important that other than gender ratio, you also get the right ratios for different ethnic groups, different religions and different political affiliations in your surveyed sample. Thinking about these ratios while architecturing your research is the basis of quota sampling. 

Unfortunately, quota sampling is inherently error-prone. It's usually performed by humans and since there is particular goal that humans are striving for (achieving a quota), it is non-random. What we observe is that, for the sake of acquiring a particular ratio, they start biasing their selection. For example, if a journalist is asked to get 50% of women responses in the survey and she is having a hard time finding random women on streets, in desperation, she may start surveying all the females in her family and friend circles just to finish the quota for females. This of course biases the female dataset heavily as the selection was based on *ease of access* and *time constraints*, which leads to *selection bias*. In this case, the bias could have skewed the dataset towards females who belong to similar social stratum. If she would have used a *random female generator* to fulfill the quota, she would have avoided the bias. 

It's interesting to note how avoidance of either of *selection bias* or *quota bias* could lead to appearance of the other. The infamous [1936 *Literary Digest* poll](https://en.wikipedia.org/wiki/The_Literary_Digest#Presidential_poll) for presidential election in USA is the poster boy for selection bias. Almost all of the survey responses (for '*who are you gonna vote for*') came from people in telephone directory, magazine subscribers and club members. At the time, this biased the dataset towards upper and middle class voters, while excluding the lower class folks. Literary Digest may have paid emphasis on the quota sampling by including correct gender and party affiliation ratios (by surveying equal number of registered Democrats and Republicans). But the surveying methods available at the time constrained them to reach out only to people from upper and middle class. This is similar to what happened to our journalist friend above. 

A simple lesson to draw from this is that whenever it comes to performing quota sampling, avoid sole responsibility on error-prone [**human decision making**](https://en.wikipedia.org/wiki/Heuristic). It will always be subject to some bias.

