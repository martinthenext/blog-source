---
Title: How to fix soft sciences (with example in medicine)
Date: 2014-01-23
---

Any article with a shouting title like that is probably written by someone who has no idea about what he/she is talking about. At least this one is: I have a Computer Science/Engineering background and never been a researcher in any kind of soft science. Nevertheless, looking at soft sciences from technical prospective may result in some interesting insights. I personally found the idea behind this article so amazing it made me want to quit everything I was doing and *do something about it*. So I feel the shouting title is appropriate. 

### What's the problem?

People who at some point understood the power of mathematics and natural sciences, including people in tech world, tend to have an opinion that soft sciences are not actual sciences. The reason for this attitude might be *lack of predictive power*. Indeed, in natural sciences we have nicely repeatable experiments: whenever you throw a rock from the same height, it will take the same time to reach ground. This allows researchers in natural sciences to come up with simple models that have a great predictive power: using them not only you can say what time it will take a rock to fall from a different height, you can send a rocket to Mars for the first time ever and know exactly what would happen. In comparison, in soft sciences models are complicated and experiments not repeatable.

One great value of science is that it helps us answer *practical* question. Natural sciences through engineering give you pretty precise answers to a lot of these. How do you build a bridge without wasting too much material? How do you make faster/safer transport? If you want to build something, models from natural sciences will help you. 

How do you run a government so that people are most satisfied? How do you teach a language in a most efficient way? How to be healthy? As soft sciences have to answer these questions, they don't have precise answers just yet. Some people say that it is because we didn't pay enough attention to them and in some time they will become as 'mathy'/precise as physics is. I tend to stick to [von Mises's](http://en.wikipedia.org/wiki/Human_Action) opinion on a difference between mechanistic and teleological paradigms, but even it soft sciences are going to become mathematical at some point, now there's not much of math in them - mostly statistics.

### Why would you care

We still need answers, that's why. We need to know what is a healthy diet, how to build effective societies and develop poor countries. Inability to get precise answers to these questions is awful. However dissatisfied we are with the result of soft science researchers' work, the problems they are trying to solve are real.

### Human expertise

When we are trying to answer a question about building bridges we go with models from natural sciences and derive our answer from them because natural sciences are good enough.  But using the same pattern in soft science related questions might be a mistake. *Why do we look for an answer about building societies like we're searching for an answer about building bridges*? 

There are some questions we don't use *knowledge* for answering, we use *experience*. There is not much science for artistic painting or making music. There is also no scientific book describing precise algorithm of being a good sales manager or designer - meaningful books are those describing their experience so that you can learn from it if it's relevant. 

Would a person trying to become a good designer learn from books containing other people's experience? Yes. Will this person then be able to better answer practical questions in their field? Yes. Would it be possible for this person to somehow transfer their skill to other people without describing experience, like we do with bridge building skill through engineering textbooks? Not necessarily.

An expert is a person who somehow has an appropriate experience in a field. We need experts because knowledge is not always transferable. For some sort of questions it doesn't look transferable at all. If we want to be able to get good answers for this type of questions, we have to somehow transfer experience instead.

### Transferring experience. Example: Collaborative filtering.

The concept of making experience based system instead of model based one can be easily illustrated with the example of collaborative filtering.

Suppose you're asked to make a system for predicting what a user would most likely want to buy from one shop, and it's 1980. You have this one expensive machine you can use for that purpose. What you do is look up some paper (*model*) from researchers in Marketing and use this *model* to compute stuff people would buy in your shop. The problem is that this model would never fit your shop because it's been fitted on someone else's shop. 

In some time machines start to become more powerful and now you can actually fit the model on your own shop's data once in a while, and then use the model to predict what people would like. At some point machines are powerful enough to allow for [collaborative filtering](http://en.wikipedia.org/wiki/Collaborative_filtering) - you don't fit a model any more. You're virtually running ad hoc query on all your shop's data every time you need to predict user's preferences. You dismissed a *model* to go with *experience* - it works better. 

The reason why model for prediction of personal preferences to be outperformed by some distance-based method might be it's complexity. That points to the fact that if models are not simple enough, it should be always better to go with experience - as long as the infrastructure allows it.

### Medicine

If everything is the way I see it, a great goal of our time (yes, I seriously think that) would be to develop infrastructure and tools for people to gather, exchange and analyze experiences of each other in all kinds of fields. I've been [interested](http://scriptogr.am/martinthenext/post/direction-for-2014) in health and [medicine](http://www.youtube.com/watch?v=SxVJoKqrOsI) for some time, this is why I decided to make an example in this field. That's nothing but a way for me demonstrate a concept - I need *way* more knowledge about how hospitals and doctors work befor I can even talk about what actually needs to be done. But the general idea should be right.

![](http://davtyan.org/blog-images/xx.jpg)

Currently doctors are being trained *medical science* for years and then required to get at least 3 years of *experience* before they are allowed to practice themselves. That might be a good indication about how experience is important in medical profession! Medical science seems to be pretty diverse and complicated - so complicated a lot of effort has been put into developing tools allowing doctors to explore relevant parts of it using computers - like [Protege](http://protege.stanford.edu/) ontology editor.

Could be, though, that medical models contained in *knowledge* are less valuable than *experience* - factual information about different medical cases. Imagine a doctor considering patient's medical case. It would be cool to allow her run queries against all medical history of all patients on Earth. This could turn out nice like in the collaborative filtering example above - models are complicated, relevant experience is valuable. Running ad hoc analysis on cases relevant to one particular case could be extremely useful. We just have to build appropriate infrastructure.

On the picture I show ontologies as a way to link hospital databases to some kind of unified terminological resource, allowing for data integration between them. This is something I had a tiny bit of experience in a magical field of Systems Engineering, and it works for data integration in industry. 

Unification of data from different medical sources can allow for performing queries and analysis over the whole body of data. Some interesting modification to widespread machine learning / statistical methods might be required for using them in a situation where data structure is inconsistent.

### Summary

In trying to find answers to questions about society, language, health and other important topics in areas where we can't have repeatable experiments and simple models, *experience* is more important than *knowledge*/science/models. Hence development of tools allowing field experts/interested people access and run ad-hoc data analysis queries on relevant historical/factual data would be more important than development of scientific models in these areas. Continuous development of computer technology would allow to perform such ad-hoc queries for increasingly bigger data amounts.
