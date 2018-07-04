---
Title: Django enumeration for model field choices
Date: 2012-03-15
Tags: ['python']
---

The problem with supplying a Django model field with choices parameter is the way you check a value of that field in an object. You do nasty things like this:

	if model_instance.choice_field == 1:

The problem of getting rid of hard-coded numbers is recognized over the internet, but I haven't found any short and understandable solution. The solution to this problem needs to work like this:

	>>> states = Enum('OPEN', 'CLOSED')
	>>> states.OPEN
	0
	>>> states.get_choices()
	((0, 'OPEN'), (1, 'CLOSED'))

Basically, we need a enumeration in python, that is ok to use as the Django `choices` model field argument. The code I've came up with is pretty short:

    class DjangoEnum(object):
        def __init__(self, *string_list):
            self.__dict__.update([(string, number) for (number, string)
                                  in enumerate(string_list)])
    
        def get_choices(self):
            return tuple(enumerate(self.__dict__.keys())) 

Of course, this only works if you use integers in your model. I use `models.PositiveSmallIntegerField` with this.

UPD. Also posted it to [DjangoSnippets](http://djangosnippets.org/snippets/2725/)
