---
Title: Nice grouping in Python
Date: 2013-12-31 
Tags: ['python']
---

Just found another cute python recipe:

    In: l = ['a', 'b', 'b', 'c', 'a']
    In: [(group, l.count(group)) for group in set(l)]
    Out: [('a', 2), ('c', 1), ('b', 2)]

Because `itertools.groupby` is kind of clumsy for simple use cases.
