# pprog

A library for Python programming

### Installation

`pip install --upgrade pprog`


### APIs

#### Functions

`identity(value, *args, **kwargs)` returns the first value `value`.

`perm(values, cycle)` permutates a list according to a cycle notation.

#### Classes

`AttrCaller(attr)` instantiates a callable object that calls the callable attribution of its argument when it is called.

`ConstantCreator(value, copy=False)` instantiates a callable object that returns the same constant when it is called.

`PermArgsExecutor(fun, perm=None)` instantiates a callable object that swaps positional arguments according to a cyclc notation. By default, it permutates the first two arguments.


### Usage Examples

```python
>>> from pprog import identity
>>> identity("value", "other_input", key="other_keyword_input")
'value'

>>> from pprog import perm
>>> perm(["a", "b", "c", "d", "e", "f", "g"], [1, 2, 4])
['a', 'c', 'e', 'd', 'b', 'f', 'g']

>>> from pprog import AttrCaller
>>> caller = AttrCaller("upper")
>>> caller("test")
'TEST'

>>> from pprog import ConstantCreator
>>> creator = ConstantCreator("value")
>>> creator()
'value'

>>> from pprog import PermArgsExecutor
>>> executor = PermArgsExecutor(range)
>>> executor(4, 2)
range(2, 4)
```
