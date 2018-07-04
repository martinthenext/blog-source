+++
date = "2016-04-29"
draft = false
title = "Ode to Hugo and itertools"
tags = ['python']
+++

If you are reading this, I actually succeeded in setting up [Hugo](https://gohugo.io) for static site generation. It is written in Go, fast and cross-platform.

Traditionally, I judge website designs by the way they can highlight code. This code, by the way, is the best thing I have seen in a year or so (originally from [StackOverflow](http://stackoverflow.com/a/22919323/211223)):

    def iter_split_by(n, iterator):                         
        """ Split an iterator into groups of n elements                                  
         Examples:                                                                        
            >>> [i for i in iter_split_by(3, iter(range(10)))]                            
            [[0, 1, 2], [3, 4, 5], [6, 7, 8], [9]]                                       
                                                                                          
        """                                                                               
        slices = (list(islice(iterator, n)) for _ in count())                             
        return takewhile(bool, slices)

Look how lazy it is. Beautiful.
