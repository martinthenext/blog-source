---
Title: String transformation with one example
Date: 2015-04-26
---

The [recent post][3] on Hacker News featured [Transformy][2], an application that allows you to transform strings e.g., change date or name formatting, without having to program anything. Instead you give it an example by transforming *one* string from your batch. It tries to infer the rule that you used and apply it to all other strings. 

I was so excited about this I killed some time and reproduced similar functionality with a hudgred lines in Python, see [here][4]. By far the script reproduces examples from the Transformly website:

    >>> transformer = StringTransformer()
    >>> transformer.train_by_example('Joel, 1949, piano', '{name: \'Joel\', instrument: \'piano\'}')
    >>> print transformer.transform('Lennon, 1940, guitar')
    {name: 'Lennon', instrument: 'guitar'}

It is obviously very limited in functionality, mainly because it requires all strings in the batch to have a *very* similar structure. Another problem is ambiguity: when you see an example like `02-02-2014 -> Day 02 Month 02 Year 2014` you cannot infer which position in the first string corresponds to days.

Naturally, this kind of ambiguity could be resolved by looking at multiple examples. This is what a (seemingly) more advanced tool, Microsoft Excel [FlashFill][1] can do. I could think of several ways to improve my script allowing for multiple examples in an imperative fashion, but something tells me that is not the way. It would be way cooler to rephrase the entire problem in probabilistic terms.

[1]: https://support.office.com/en-us/article/Use-AutoFill-and-Flash-Fill-2e79a709-c814-4b27-8bc2-c4dc84d49464?ui=de-DE&rs=en-001&ad=DE&fromAR=1&omkt=en-001
[2]: http://www.transformy.io
[3]: https://news.ycombinator.com/item?id=9432949
[4]: https://gist.github.com/martinthenext/fc989ffa6ec84ee09962
