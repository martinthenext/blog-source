---
Title: Meta class inheritance in Django
Date: 2012-03-22
---
Here:

    >>> class alpha(object):
    	class beta:
    		sigma = 3
    
    		
    >>> class alpha2(alpha):
    	class beta(alpha.beta):
    		sigma = 4
    		delta = {'a': 5}
    
    		
    >>> a = alpha2()
    >>> a.beta.sigma
    4
