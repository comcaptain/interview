---
title: Javascript test
---
## Javascript test

*Please do not use any digital device (so, no Google, no browser developer tool...) when doing this test.*

### Question 1

```javascript
// Question: What is the value of "a" and why?
var a = 1 === '1';

// Question: what is the value of "b" and why?
var b = 1 == '1';
```

### Answer: <br><br>

### Question 2

There are two clients: the first client's id is 1, name is 'Jane'; the second client's id is 2, name is 'Amy'.

Please write JSON string for these two clients

### Answer:<br><br>

### Question 3

```html
<table>
	<tr>
		<td class="name">Emma</td>
		<td><button class="aha">click me</button></td>
	</tr>
	<tr>
		<td class="name">Olivia</td>
		<td><button class="aha">click me</button></td>
	</tr>
	<tr>
		<td class="name">Ava</td>
		<td><button class="aha">click me</button></td>
	</tr>
	<tr>
		<td class="name">Isabella</td>
		<td><button class="aha">click me</button></td>
	</tr>
	<tr>
		<td class="name">Sophia</td>
		<td><button class="aha">click me</button></td>
	</tr>
	<tr>
		<td class="name">Mia</td>
		<td><button class="aha">click me</button></td>
	</tr>
	<!-- There are a thousnd more rows... -->
</table>
```

Please write js code to implement this requirement: when clicking each button in the table, alert correponding row's name. e.g. If you click the second row's button, then alert "Oliva".

*You are NOT allowed to modify the html, and the js you write will be put into a seperate js file. It would be great if you can write pure js, but using jQuery is also allowed*

### Answer: <br><br><br><br><br><br><br><br>

### Question 4

```javascript
var length = 10;
function fn()
{
	console.log(this.length);
}

var obj =
{
  length: 5,
  method: function()
  {
  	fn();
    fn.call(this)
  }
}

fn();
obj.method();
```

What is the output and why?

### Answer: <br><br><br>

### Question 5

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(function() { console.log(i); }, 1000 + i);
}
```

What is the output and why?

### Answer: <br><br><br>

