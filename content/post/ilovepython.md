---
Title: I love python
Date: 2013-12-09
Tags: ['python']
---

This:

    >>>class some_class(object):
    ...  def beep(self):
    ...    print 'beep'

    >>># passing class as a parameter
    ...def do(cls):
    ...  inst = cls()
    ...  inst.beep()

    >>>do(some_class)
    beep

Also, [sklearn](http://scikit-learn.org/) is amazing - well documented and really easy to use.
