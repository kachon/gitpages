Title: Python Static Variables
Category: Python
Tags: Python
Author: KaChon Lei
Summary: Notes about Python staic variables

To delcare a static variable in Python.  Delcare it outside the __init__ method.

    :::python
	class TestClass1:
	    class_prop = 111

	print TestClass1.class_prop ---> 111

To delcare a static function in Python.  Delcare a function with a @staticmethod decorator.

    :::python
	class TestClass1:
		class_prop = 111
	
		@staticmethod
	    	def print_class_prop():
			print TestClass1.class_prop

	print TestClass1.print_class_prop() ---> 111
	
Another way for implementing print_class_prop() is to use @classmethod decorator.  A function defined with @classmethod decorator will receive a cls argument.  This is useful when we have a inheritance situation.

    :::python
	class TestClass1:
		class_prop = 111
		
		@staticmethod
		def print_class_prop(cls):
			print cls.class_prop

	class TestClass2:
		class_prop = 222
	
	print TestClass1.print_class_prop() ---> 111	
	print TestClass2.print_class_prop() ---> 222
