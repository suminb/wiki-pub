Python
======

List Comprehension
------------------

.. code-block:: python

    [(i, j) for i in range(10) for j in range(10)]


Overriding Global Functions
---------------------------

In Python, everything can be changed in run-time. Even built-in functions
like ``print()``. Suppose we override ``print()`` as follows:

.. code::

    print = None

Then we are no longer able to use the built-in function.

.. code::

    >>> print('Hello World!')
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    TypeError: 'NoneType' object is not callable

The most tempting solution to this is probably re-starting the interpreter
(or whatever runtime we are on). Another way would be delete the global
variable ``print`` as follows:

.. code::

    del globals()['print']

Then our ``print()`` function is back alive.

.. code::

    >>> print('Hello World!')
    Hello World!
