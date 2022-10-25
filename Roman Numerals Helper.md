---
date created: 2022-10-20 17:00
date updated: 2022-10-25 10:54
tags:
  - algorithms
---

Create a RomanNumerals class that can convert a roman numeral to and from an integer value. It should follow the API demonstrated in the examples below. Multiple roman numeral values will be tested for each helper method.

Modern Roman numerals are written by expressing each digit separately starting with the left most digit and skipping any digit with a value of zero. In Roman numerals 1990 is rendered: 1000=M, 900=CM, 90=XC; resulting in MCMXC. 2008 is written as 2000=MM, 8=VIII; or MMVIII. 1666 uses each Roman symbol in descending order: MDCLXVI.

Input range: `1 <= n < 4000`

In this kata `4` should be represented as `IV`, NOT as `IIII` (the "watchmaker's four").

**Examples**

```python
RomanNumerals.toRoman(1000);
RomanNumerals.fromRoman('M');
```

**Help**

| Symbol | Value |
| ------ | ----- |
| I      | 1     |
| IV     | 4     |
| V      | 5     |
| X      | 10    |
| L      | 50    |
| C      | 100   |
| D      | 500   |
| M      | 1000  |

```python
ROMANS = {
    "M": 1000,
    "CM": 900,
    "D": 500,
    "C": 100,
    "XC": 90,
    "L": 50,
    "X": 10,
    "V": 5,
    "IV": 4,
    "I": 1,
}

class RomanNumerals:
    def to_roman(n):
        s = ""
        for key, value in ROMANS.items():
            while n % value != n:
                n = n - value
                s += key
        return s

    def from_roman(r):
        s = 0
        for key, value in ROMANS.items():
            while r.startswith(key):
                r = r[len(key) :]
                s += value
        return s
```
