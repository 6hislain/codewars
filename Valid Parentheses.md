Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return `true` if the string is valid, and `false` if it's invalid.

__Examples__
"()"                   => true
")(()))"               => false
"("                    => false
"(())((()())())"      => true

__Constraints__
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