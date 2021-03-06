# pyinttupleset

Set of integer tuples for python

Supports adding, iterations and presence check

Example:

```python
import itertools
import os
from pyinttupleset import PyIntTupleSet

p = PyIntTupleSet()

it = itertools.product(range(100000), repeat=10)
for _ in range(50000000):
    p.add(next(it))

print([1, 2, 3, 4, 5, 6, 7, 8, 9, 10] in p)
print([0, 0, 0, 0, 0, 0, 0, 0, 9, 10] in p)

print(f'{len(p)} objects use')
os.system(f'pmap -p {os.getpid()} | tail -n 1')
print('memory')

for i, e in enumerate(p):
    if i > 1000000:
        print(e)
    if i > 1000010:
        break
```

Output:

```
False
True
50000000 objects use
 total          5493612K
memory
[0, 0, 0, 0, 0, 0, 0, 0, 10, 1]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 2]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 3]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 4]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 5]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 6]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 7]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 8]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 9]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 10]
[0, 0, 0, 0, 0, 0, 0, 0, 10, 11]
```
