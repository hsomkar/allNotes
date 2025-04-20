- A regular expression is an object that describes a pattern of characters.
- It is normally used in form validation
- **Syntax:**
- A regular expression could be defined with the RegExp() constructor, as follows:

		`var pattern = new RegExp(pattern, attributes); ` 
		(OR _simply)_  
		`var pattern = /pattern/attributes;`

- **pattern**: A string that specifies the pattern of the regular expression or another regular expression.
- **attributes**: An optional string containing any of the "g", "i", and "m" attributes that specify global, case-insensitive, and multiline matches, respectively.
## Brackets

| Expression | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| [...]      | Any one character between the brackets.                        |
| [^...]     | Any one character not between the brackets.                    |
| [0-9]      | It matches any decimal digit from 0 through 9.                 |
| [a-z]      | It matches any character from lowercase a through lowercase z. |
| [A-Z]      | It matches any character from uppercase A through uppercase Z. |
| [a-Z]      | It matches any character from lowercase a through uppercase Z. |
## Quantifiers

| Expression | Description                                                      |
| ---------- | ---------------------------------------------------------------- |
| p+         | It matches any string containing at least one p.                 |
| p*         | It matches any string containing zero or more p's.               |
| p?         | It matches any string containing one or more p's.                |
| p{N}       | It matches any string containing a sequence of N p's             |
| p{2,3}     | It matches any string containing a sequence of two or three p's. |
| p{2, }     | It matches any string containing a sequence of at least two p's. |
| p$         | It matches any string with p at the end of it.                   |
| ^p         | It matches any string with p at the beginning of it.             |
## RegExp Methods

| Method     | Method                                                                                                      |
| ---------- | ----------------------------------------------------------------------------------------------------------- |
| exec()     | Executes a search for a match in its string parameter.                                                      |
| test()     | Tests for a match in its string parameter.                                                                  |
| toSource() | Returns an object literal representing the specified object; you can use this value to create a new object. |
| toString() | Returns a string representing the specified object.                                                         |
### Example
```
<script type="text/javascript">
var str = "Javascript is an interesting scripting language";
var re = new RegExp( "script", "g" );
var result = re.test(str);
document.write("Test 1 - returned value : " + result);
re = new RegExp( "pushing", "g" );
var result = re.test(str);
document.write("<br />Test 2 - returned value : " + result);
</script>
```
### Output
Test 1 - returned value : true  
Test 2 - returned value : false

