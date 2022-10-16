---
date created: 2022-10-16 06:17
date updated: 2022-10-16 06:20
tags:
  - algorithms
---

Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return `true` if the string is valid, and `false` if it's invalid.

**Examples**
"()"                   => true
")(()))"               => false
"("                    => false
"(())((()())())"      => true

**Constraints**
`0 <= input.length <= 100`

```javascript
function validParentheses(parens) {
	var n = 0;
	for (var i = 0; i < parens.length; i++) {
		if (parens[i] == '(') n++;
		if (parens[i] == ')') n--;
		if (n < 0) return false;
	}

	return n == 0;
}
```
