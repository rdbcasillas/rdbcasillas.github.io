---
layout: post
title: "Towards a better commenting system"
category: essays

---

###What is a civil conversation?
We are a species that loves to communicate opinions and ideas. Opinions and ideas are a form of
advertisement that market the audience about our personalities. Until the arrival of the internet,
for most people(not businesses) the medium for these advertisements used to be face to face talk or
exchange of letters. Since the 1990s though, the marketing tools have transformed and the most
popular ones today include sites like Twitter, Facebook, Reddit and other massive creators of
information. Information in the form of opinions and feelings of people. A person sits behind a
screen fearlessly and engages in conversations in a way like they never would in person. And that's why this is no harmless marketing. Our main motive isn't always to maximize profit by being diplomatic or kind in expressing our opinions. It often requires(mandates even) that we use aggressive language, make snarky comments by using ad hominems and troll the [other side](https://en.wikipedia.org/wiki/Tribalism). Why not just politely argue using the new meduim, you ask?
Two reasons:

1. There are no major consequences. Especially because the new medium allows one to stay anonymous. A ten year old can easily create hundreds of fake accounts to spam forums where he disagrees with the majority. But this is mostly true for people without a known identity. With easy trolling, even  trivial opinions by minutely famous people can be quickly turned into racist and offensive slurs. So no major consequences unless you happen to be remotely famous(this generalized statement isn't always
true. Check [this poor lady's](http://www.nytimes.com/2015/02/15/magazine/how-one-stupid-tweet-ruined-justine-saccos-life.html?_r=0) story). 

2. Its not catchy enough to spread like wildfire. Go to Youtube or Facebook and the most liked comments on a post will usually be shallow one liners that are either overly congratulatory or angry(depending on the mood of the majority towards that video). Sober and lengthy comments aren't sexy enough and they usually require more thinking. Not a good replicating virus because the content of its DNA is ineffective towards host's attention span. 


So after observing these behaviors over the past few years, it feels safe to assume that the majority
of humanity, left on its own, is incapable of having civilized and rational discussions on public forums. This is more so when it comes to emotionally motivated conversations in domains like Politics, Religion or Surveillance/Privacy. These topics attract all kinds of biases and fallacies 
that human mind can fall prey to. And none of this is very surprising when you consider the strong association of these beliefs to a person's identity. As I noted above, the most emotionally driven comments or ideas(that lack actual content) are [more likely to spread](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=1528077). Hence I am interested in commenting systems that just by their usage help in motivating the users to [disagree properly](http://www.paulgraham.com/disagree.html). Lets first look at some solutions that have been offered in the past. 


###The well known problem of ranking comments
The problem of ranking comments and encouraging healthy discourse is a fascinating one and companies involved in managing forums have been trying different techniques to make the system better. Back in 2009, [Reddit introduced the "best" option for sorting](http://www.redditblog.com/2009/10/reddits-new-comment-sorting-system.html) that overcame the problem of comments that would show up at the top largely because they were posted right after the story was posted. As Randall Munroe explains:

>reddit is heavily biased toward comments posted early. When a mediocre joke gets posted in the first hour a story is up, it will become the top comment if it's even slightly funny. (I know this particularly well because I have dozens of reddit fake identities and with them have posted hundreds of mediocre jokes.) The reason for this bias is that once a comment gets a few early upvotes, it's moved to the top. The higher something is listed, the more likely it is to be read (and voted on), and the more votes the comment gets. It's a feedback loop that cements the comment's position, and a comment posted an hour later has little chance of overtaking it -- even if people reading it are upvoting it at a much higher rate.

But obviously, this solution doesn't address the issue about the quality of the comments on Reddit which have been degrading consistently over the last few years. This isn't surprising since any community that grows exponentially will generally bring more noise than signal. And its not just the quality that has degraded. There is also the issue of lack of diversity. Contrary opinions are just not very welcome once you have a majority that likes to see things in black and white. So downvotes end up meaning disagreements and bury a contrarian viewpoint into oblivion even if it was articulated eloquently, in turn converting a forum into an [echo chamber](https://en.wikipedia.org/wiki/Echo_chamber_%28media%29). There are some sub communities in reddit(called subreddits) which never attract a large audience and they still remain great places to hang out in. But reddit provides no mechanism other than the "report" button or heavy moderation(which can go terribly wrong) to **encourage** rational discourse. 
 

But coming back to the problem of ranking comments, a system that can recognise what echo chamber
means and gives a particular thread(of comments) some value based on the amount of herd mentality or
lack of contrary opinion will at least keep us aware of the level of bias that such a thread might be
infected with(This is less applicable to threads discussing natural sciences and more to sociological
sciences a.k.a humanities). At this point though, complex ranking algorithms only work towards keeping a good mixture of old, new and popular comments at the top depending on factors like "time since main post", "user's karma", "upvotes/downvotes ratio" etc. Hacker News's(HN) ranking algorithm is one of the most complex that I have seen. These strategies obviously help the readers to witness the best comments(decided by the community) at the top but still doesn't address the issue of **encouraging** civil discourse. Since the HN audience is biased towards people with better sense of civility, the comments there aren't a good measure of the population of comments in general. But [it has been noted](https://news.ycombinator.com/item?id=4396747.) that the growth of HN has led to
some degradation in quality as well and there are [plausible complaints](http://mjg59.dreamwidth.org/28232.html) about HN being an echo chamber too. But at least its run by people who welcome contructive criticism and are always [looking to improve the system](https://news.ycombinator.com/item?id=7605973).


###Google's failed attempt and arrival of Discourse
In 2013, Youtube [tried to tackle spams and trolls](http://www.reelseo.com/youtube-comments-system-rolling/) and [failed miserably](http://www.pcmag.com/article2/0,2817,2427715,00.asp). They infamously started forcing people to have a Google+ account to be able to comment and this was at least superficially, argued as a measure to reduce the level of abuse or vulgarness in comments. But nothing changed for the better(in fact, the situation became worse) and they finally [decided to let go of it](http://www.theverge.com/2015/7/27/9047785/youtube-ditching-google-plus-requirement). 

[Discourse](https://www.discourse.org/) is a most promising tool that is in the business of promoting healthy discourse. Their [Universal Rules of Civilized Discourse](http://blog.discourse.org/2013/03/the-universal-rules-of-civilized-discourse/) highlight the major sources of contamination in a healthy online communication. Here is what they 
aspire to achieve:

>Our trust system means that the community builds a natural immune system to defend itself from trolls, bad actors, and spammers — and the most engaged community members can assist in the governance of their community. We put a trash can on every street corner with a simple, low-friction flagging system. Positive behaviors are encouraged through likes and badges. We gently, constantly educate members in a just-in-time manner on the universal rules of civilized discourse.


Although they do a 
decent job of encouraging healthy discussions and reminding users to [not be a dick](http://wilwheaton.net/2012/12/keep-calm-and-dont-be-a-dick/), there is nothing in the system itself that pushes the community to better understand the nature of a quality comment. A comment
that either reflects pure curiosity, honest skepticism or just willingness to participate in a constructive way that adds to the knowledge base of the thread. Because of 
ambiguities associated with the meaning of these traits, its super hard to create such programs. Discourse is definitely a step in the right direction albeit a small one.


###Proposed ideas

In my hunt for the propsed methods to improve the situation, I came across an idea on HN about a commenting system that consists of different "leagues":

>There needs to be a way where there is automatic segmenting based on quality of commentary. Maybe like a Major leagues, minor leagues and troll leagues, where there are two or three simultaneous threads going on. People who've never commented before and have no karma end up in the minor leagues by default. If they get upvoted enough their, their comments go to the major leagues. Likewise, if their comments get downvoted enough it ends up in the troll leagues, where the trolls can quibble among one another.

I like this idea but identifying trolls from serious arguments that are politically incorrect isn't simple especially when you keep into account the high levels of sensitivity. Its not very hard to  offend people nowadays and one needs to tread carefully when being brutally honest. If we allow people to use votes to make the decision of relegating someone to a league of trolls just because they happen to "offend" the majority, then its again a failed system that selectively chooses the people who are like minded in their political ideologies. And this will always remain a problem with a community of people who get to decide who stays in their league. So there isn't any completely objective basis on which to relegate(except in obvious cases where the commenter says nothing other than a derogatory or congratulatory statements which never contribute a dime to the conversation). 


###Machine Learning to the rescue?
(Disclaimer: Heavy speculation follows due to ignorance of learning techniques)

That's where I feel [Machine Learning](https://en.wikipedia.org/wiki/Machine_learning) will have to kick in. If we can use a [natural language learning algorithm](https://en.wikipedia.org/wiki/Natural_language_processing) that does a decent job of concluding which comments comprise of a healthy or rational ones and which ones qualify as fluff or troll, we will have some objective basis on which to relegate users to a troll league. Good news is that there are many websites to learn from like lesswrong and Hackernews where there are millions of comments that will qualify as healthy. The signal to noise ratio is extremely high for these websites which will make them a perfect dataset for understanding the meaning of a good comment. On the other hand, comments on Youtube and some horrible news website like Drudge Report and Salon have some of the most awful comments sections you will find on the interwebz. These will help in learning the nature of unhealthy comments. I haven't thought about the features of comments being analyzed that will allow the algorithm to tag them as "A", "B" or "C"(those being the name of different leagues) but one (not so great) feature that immediately comes to mind is the length of the comment. There are many exceptions obviously but in my experience longer comments tend to be more often healthy than not. But of course Mark Twain would be [horrified](https://www.goodreads.com/quotes/21422-i-didn-t-have-time-to-write-a-short-letter-so) with such weight assignment. Better feature detection can only really happen once we make some progress in creating algorithms that understand the English language.

Another important thing that worries me is the constant digression from the original topic of discussion. Sometimes they are great and can lead to insighful ideas but on most occassions they distract me as a reader who is only concerned with the primary discussion triggered either by an article or an event. Could there be a way to "sense" digression and allow the reader to filter out the comments that initiate digression, along with their children(children being all the descendents  of the comments that digress)?  Its again tempting to think of Machine Learning(more specifically [discourse analysis](https://en.wikipedia.org/wiki/Discourse_analysis)) as a solution to this problem too! But with our current understanding, there is no question that high number of false positives and true negatives will be disastrous for the system that tries to understand and detect digression. 

Finally, we would need an algorithm that can go through the comment and validate its verity by looking for unstated assumptions or taken for granted facts without any good resources to back them up(exceptions would include safe to assume facts like like "Earth goes around Sun", "Evolution by natural selection" etc.). So even though it might be a great comment and deserves to stay in **A league**, there could be a tag attached to it signifying that it makes outstanding claims without decent references or emperical evidence. This will be very similar to Wikipedia's strategy of checking citations or sources for something that author of the article claims as a fact. This final strategy will heavily increase the standard of quality. One will get to filter even the comments within "A league" based on the tags attached to them. 

Contemplation or hypothesizing should obviously not come under this scrutiny and one can simply have some options to chose the level of belief they attach to their comment. For example, If I make a hypothesis, I get to choose a tag called "speculation" that disallows the algorithm to run its bullshit detectors on my comment. Hopefully the community will be constantly helping the algorithm to learn because initially there are bound to be many false positives and false negatives. 

Another idea that we need to look into is tools that allow humans to write structured comments. This would mean that these tools will make it convenient for people to structure their comments in a more methodical way which will then allow these tools to better perform language processing. Hypotheses, anecdotes, facts etc. are much more easier to deduce once the user can either annotate their comments or use specific keywords to make annotation easier for algorithms. 

Since advances in machine learning are unpredictable, its hard to predict how far we are from proper exectution of these ideas but there is no question that future comment systems will be monitored by AI that will filter bullshit and incentivize the members to engage in a rational civil discourse.  