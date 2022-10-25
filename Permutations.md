---
date created: 2022-10-25 11:00
date updated: 2022-10-25 11:01
tags:
  - permutations
  - strings
  - algorithms
---

In this kata you have to create all permutations of a non empty input string and remove duplicates, if present. This means, you have to shuffle all letters from the input in all possible orders.

**Examples:**

```
* With input 'a'
* Your function should return: ['a']
* With input 'ab'
* Your function should return ['ab', 'ba']
* With input 'aabb'
* Your function should return ['aabb', 'abab', 'abba', 'baab', 'baba', 'bbaa']
```

The order of the permutations doesn't matter

```python
import itertools

def permutations(string):
	return list(''.join(p) for p in set(itertools.permutations(string)))
```
